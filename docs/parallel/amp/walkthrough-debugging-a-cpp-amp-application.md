---
title: 逐步解說：偵錯 C++ AMP 應用程式
ms.date: 11/19/2018
helpviewer_keywords:
- debugging, C++ Accelerated Massive Parallelism
- C++ AMP, debugging
- C++ Accelerated Massive Parallelism, debugging
- debugging, C++ AMP
ms.assetid: 40e92ecc-f6ba-411c-960c-b3047b854fb5
ms.openlocfilehash: 610cf317982204715d55d12ece510cb477543f4d
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176688"
---
# <a name="walkthrough-debugging-a-c-amp-application"></a>逐步解說：偵錯 C++ AMP 應用程式

本主題示範如何使用 c + + Accelerated Massive Parallelism (c + + AMP)，以善用圖形處理單元 (GPU) 的應用程式進行偵錯。 它會使用加總大型整數陣列的平行方式來降低程式。 這個逐步解說將說明下列工作：

- 正在啟動 GPU 偵錯工具。

- 檢查 [GPU 執行緒] 視窗中的 GPU 執行緒。

- 使用**平行堆疊**同時觀察多個 GPU 執行緒的呼叫堆疊 視窗。

- 使用**平行監看式**視窗來查看跨多個執行緒的單一運算式的值，在相同的時間。

- 加上旗標、 凍結、 解除凍結，和群組 GPU 執行緒。

- 在程式碼中執行所有執行緒的圖格，以特定的位置。

## <a name="prerequisites"></a>必要條件

在開始本逐步解說之前：

- 讀取[c + + AMP 概觀](../../parallel/amp/cpp-amp-overview.md)。

- 請確定這一行文字編輯器中顯示數字。 如需詳細資訊，請參閱 <<c0> [ 如何： 在編輯器中顯示行號](/visualstudio/ide/reference/how-to-display-line-numbers-in-the-editor)。

- 請確定您執行 Windows 8 或 Windows Server 2012，以支援在軟體模擬器上偵錯。

[!INCLUDE[note_settings_general](../../mfc/includes/note_settings_general_md.md)]

### <a name="to-create-the-sample-project"></a>建立範例專案

1. 啟動 Visual Studio。

2. 在功能表列上，選擇 [檔案] > [新增] > [專案]。

3. 底下**已安裝**在 [範本] 窗格中，選擇**Visual c + +**。

4. 選擇**Win32 主控台應用程式**，型別`AMPMapReduce`中**名稱** 方塊中，然後選擇**確定** 按鈕。

5. 選擇 [下一步] 按鈕。

6. 清除**先行編譯標頭**核取方塊，然後再選擇**完成** 按鈕。

7. 在 [**方案總管] 中**，從專案刪除 stdafx.h、 targetver.h 和 stdafx.cpp。

8. 開啟 AMPMapReduce.cpp，並以下列程式碼取代其內容。

```cpp
    // AMPMapReduce.cpp defines the entry point for the program.
    // The program performs a parallel-sum reduction that computes the sum of an array of integers.

    #include <stdio.h>
    #include <tchar.h>
    #include <amp.h>

    const int BLOCK_DIM = 32;

    using namespace concurrency;

    void sum_kernel_tiled(tiled_index<BLOCK_DIM> t_idx, array<int, 1> &A, int stride_size) restrict(amp)
    {
        tile_static int localA[BLOCK_DIM];

        index<1> globalIdx = t_idx.global * stride_size;
        index<1> localIdx = t_idx.local;

        localA[localIdx[0]] =  A[globalIdx];

        t_idx.barrier.wait();

        // Aggregate all elements in one tile into the first element.
        for (int i = BLOCK_DIM / 2; i > 0; i /= 2)
        {
            if (localIdx[0] < i)
            {

                localA[localIdx[0]] += localA[localIdx[0] + i];
            }

            t_idx.barrier.wait();
        }

        if (localIdx[0] == 0)
        {
            A[globalIdx] = localA[0];
        }
    }

    int size_after_padding(int n)
    {
        // The extent might have to be slightly bigger than num_stride to
        // be evenly divisible by BLOCK_DIM. You can do this by padding with zeros.
        // The calculation to do this is BLOCK_DIM * ceil(n / BLOCK_DIM)
        return ((n - 1) / BLOCK_DIM + 1) * BLOCK_DIM;
    }

    int reduction_sum_gpu_kernel(array<int, 1> input)
    {
        int len = input.extent[0];

        //Tree-based reduction control that uses the CPU.
        for (int stride_size = 1; stride_size < len; stride_size *= BLOCK_DIM)
        {
            // Number of useful values in the array, given the current
            // stride size.
            int num_strides = len / stride_size;

            extent<1> e(size_after_padding(num_strides));

            // The sum kernel that uses the GPU.
            parallel_for_each(extent<1>(e).tile<BLOCK_DIM>(), [&input, stride_size] (tiled_index<BLOCK_DIM> idx) restrict(amp)
            {
                sum_kernel_tiled(idx, input, stride_size);
            });
        }

        array_view<int, 1> output = input.section(extent<1>(1));
        return output[0];
    }

    int cpu_sum(const std::vector<int> &arr) {
        int sum = 0;
        for (size_t i = 0; i < arr.size(); i++) {
            sum += arr[i];
        }
        return sum;
    }

    std::vector<int> rand_vector(unsigned int size) {
        srand(2011);

        std::vector<int> vec(size);
        for (size_t i = 0; i < size; i++) {
            vec[i] = rand();
        }
        return vec;
    }

    array<int, 1> vector_to_array(const std::vector<int> &vec) {
        array<int, 1> arr(vec.size());
        copy(vec.begin(), vec.end(), arr);
        return arr;
    }

    int _tmain(int argc, _TCHAR* argv[])
    {
        std::vector<int> vec = rand_vector(10000);
        array<int, 1> arr = vector_to_array(vec);

        int expected = cpu_sum(vec);
        int actual = reduction_sum_gpu_kernel(arr);

        bool passed = (expected == actual);
        if (!passed) {
            printf("Actual (GPU): %d, Expected (CPU): %d", actual, expected);
        }
        printf("sum: %s\n", passed  "Passed!" : "Failed!");

        getchar();

        return 0;
    }
```

9. 在功能表列上，依序選擇 [檔案] > [全部儲存]。

10. 在 **方案總管 中**，開啟捷徑功能表**AMPMapReduce**，然後選擇 **屬性**。

11. 在 **屬性頁**對話方塊的 **組態屬性**，選擇  **C/c + +** > **先行編譯標頭**。

12. 針對**先行編譯標頭**屬性中，選取**未使用先行編譯標頭**，然後選擇**確定**  按鈕。

13. 在功能表列上選擇 [建置] > [建置解決方案]。

## <a name="debugging-the-cpu-code"></a>CPU 程式碼偵錯

在此程序中，您將使用本機 Windows 偵錯工具，以確定此應用程式中的 CPU 程式碼正確無誤。 特別有趣的是此應用程式中的 CPU 程式碼區段`for`迴圈`reduction_sum_gpu_kernel`函式。 它可控制樹狀結構基礎平行約化 GPU 上執行。

### <a name="to-debug-the-cpu-code"></a>若要偵錯的 CPU 程式碼

1. 在 **方案總管 中**，開啟捷徑功能表**AMPMapReduce**，然後選擇 **屬性**。

2. 在 **屬性頁**對話方塊的 **組態屬性**，選擇 **偵錯**。 確認**本機 Windows 偵錯工具**中選取**偵錯工具啟動**清單。

3. 返回**程式碼編輯器**。

4. 在下圖中 （大約幾行 67 程式碼行 70） 所示的程式碼行上設定中斷點。

   ![CPU 中斷點](../../parallel/amp/media/campcpubreakpoints.png "CPU 中斷點") <br/>
   CPU 中斷點

5. 在功能表列上，依序選擇 [偵錯] > [開始偵錯]。

6. 在 [**區域變數**] 視窗中，觀察到的值`stride_size`程式碼行 70 的中斷點為止。

7. 在功能表列上，依序選擇 [偵錯] > [停止偵錯]。

## <a name="debugging-the-gpu-code"></a>偵錯 GPU 程式碼

本節說明如何偵錯 GPU 程式碼，也就是包含的程式碼中`sum_kernel_tiled`函式。 GPU 程式碼會計算總和的每個 「 區塊 」 的整數，以平行方式。

### <a name="to-debug-the-gpu-code"></a>若要偵錯 GPU 程式碼

1. 在 **方案總管 中**，開啟捷徑功能表**AMPMapReduce**，然後選擇 **屬性**。

2. 在 **屬性頁**對話方塊的 **組態屬性**，選擇 **偵錯**。

3. 在 **偵錯工具來啟動**清單中，選取**本機 Windows 偵錯工具**。

4. 在 **偵錯工具類型**清單中，確認**自動**已選取。

    **自動**做為預設值。 在 Windows 10 之前**僅限 GPU**是必要的值，而不是**自動**。

5. 選擇 [確定]  按鈕。

6. 下圖所示，請在行 30，設定中斷點。

   ![GPU 中斷點](../../parallel/amp/media/campgpubreakpoints.png "GPU 中斷點") <br/>
   GPU 中斷點

7. 在功能表列上，依序選擇 [偵錯] > [開始偵錯]。 在 GPU 偵錯，因為在 CPU 上執行這些程式碼行時，不會執行行 67 和 70 的 CPU 程式碼中的中斷點。

### <a name="to-use-the-gpu-threads-window"></a>若要使用 [GPU 執行緒] 視窗

1. 若要開啟  **GPU 執行緒**視窗，請在功能表列上，選擇**偵錯** > **Windows** > **GPU 執行緒**。

   您可以檢查的狀態中的 GPU 執行緒**GPU 執行緒**出現的視窗。

2. 停駐**GPU 執行緒**視窗底部的 Visual Studio。 選擇**展開執行緒切換** 按鈕以顯示 tile 和執行緒的文字方塊。 **GPU 執行緒**如下圖所示，視窗會顯示作用中和已封鎖的 GPU 執行緒的總數。

   ![GPU 執行緒 視窗，顯示 4 個使用中執行緒](../../parallel/amp/media/campc.png "顯示 4 個使用中執行緒的 [GPU 執行緒] 視窗") <br/>
   [GPU 執行緒] 視窗

   有 313 配置給這項計算的圖格。 每個圖格包含 32 個執行緒。 因為本機 GPU 偵錯發生在軟體模擬器上，有四個作用中的 GPU 執行緒。 四個執行緒同時執行的指示，並會繼續在一起的下一個指令。

   在 [ **GPU 執行緒**] 視窗中，有作用中的四個 GPU 執行緒和 28 的 GPU 執行緒在遭到封鎖[tile_barrier:: wait](reference/tile-barrier-class.md#wait)第 21 行定義在陳述式 (`t_idx.barrier.wait();`)。 所有 32 個 GPU 執行緒屬於第一個磚， `tile[0]`。 箭號會指向包含目前執行緒的資料列。 若要切換到不同的執行緒，請使用下列方法之一：

    - 在切換執行緒的資料列中**GPU 執行緒** 視窗中，開啟捷徑功能表，然後選擇**切換至執行緒**。 如果資料列都代表一個以上的執行緒，您將會切換至執行緒座標的第一個執行緒。

    - 在對應的文字方塊中輸入 tile 和執行緒的執行緒值，然後選擇**交換器執行緒** 按鈕。

   **呼叫堆疊**視窗會顯示目前的 GPU 執行緒的呼叫堆疊。

### <a name="to-use-the-parallel-stacks-window"></a>使用 [平行堆疊] 視窗

1. 若要開啟 **平行堆疊**視窗，請在功能表列上，選擇**偵錯** > **Windows** > **平行堆疊**.

   您可以使用**平行堆疊**同時檢查多個 GPU 執行緒的堆疊框架的視窗。

2. 停駐**平行堆疊**視窗底部的 Visual Studio。

3. 請確定**執行緒**中左上角的清單中選取。 在下圖中，**平行堆疊** 視窗會顯示呼叫堆疊已取得焦點的檢視中的 GPU 執行緒**GPU 執行緒**視窗。

   ![平行堆疊 視窗，顯示 4 個使用中執行緒](../../parallel/amp/media/campd.png "顯示 4 個使用中執行緒的平行堆疊 視窗") <br/>
   [平行堆疊] 視窗

   32 個執行緒發生從`_kernel_stub`中的 lambda 陳述式`parallel_for_each`函式呼叫然後`sum_kernel_tiled`函式，平行約化發生的位置。 28 超出 32 個執行緒已進入[tile_barrier:: wait](reference/tile-barrier-class.md#wait)陳述式，將持續封鎖在列 22，而其他的 4 個執行緒保持作用中和`sum_kernel_tiled`第 30 行函式。

   您可以檢查 GPU 執行緒中所提供的屬性**GPU 執行緒** 視窗中的豐富資料提示方塊**平行堆疊**視窗。 若要這樣做，請將滑鼠指標上的堆疊框架**sum_kernel_tiled**。 下圖顯示資料提示方塊。

   ![平行堆疊 視窗的 DataTip](../../parallel/amp/media/campe.png "平行堆疊 視窗的 DataTip") <br/>
   GPU 執行緒資料提示方塊

   如需詳細資訊**平行堆疊** 視窗中，請參閱[使用平行堆疊視窗](/visualstudio/debugger/using-the-parallel-stacks-window)。

### <a name="to-use-the-parallel-watch-window"></a>若要使用平行監看式視窗

1. 若要開啟 **平行監看式**視窗，請在功能表列上，選擇**偵錯** > **Windows** > **平行監看式**  > **平行監看式 1**。

   您可以使用**平行監看式**視窗，以跨多個執行緒檢查運算式的值。

2. 停駐**平行監看式 1**視窗底部的 Visual Studio。 資料表中有 32 個資料列**平行監看式**視窗。 每個對應至出現在 GPU 執行緒視窗的 GPU 執行緒並**平行堆疊**視窗。 現在，您可以輸入您想要跨所有 32 個 GPU 執行緒檢查其值的運算式。

3. 選取 **新增監看式**資料行標頭，輸入`localIdx`，然後選擇**Enter**索引鍵。

4. 選取**新增監看式**再次資料行標頭中，輸入`globalIdx`，然後選擇**Enter**索引鍵。

5. 選取**新增監看式**再次資料行標頭中，輸入`localA[localIdx[0]]`，然後選擇**Enter**索引鍵。

   您可以選取其對應的資料行標頭來排序所指定的運算式。

   選取  **localA [localIdx [0]]** 排序資料行的資料行標頭。 下圖顯示結果的排序依據**localA [localIdx [0]]**。

   ![已排序的結果使用平行監看式視窗](../../parallel/amp/media/campf.png "已排序的結果，[平行監看式] 視窗") <br/>
   排序結果

   您可以匯出中的內容**平行監看式**選擇 Excel 視窗**Excel**  按鈕，然後選擇**在 Excel 中開啟**。 如果您有在您的開發電腦上安裝 Excel 時，這會開啟 Excel 工作表，包含的內容。

6. 在右上角**平行監看式** 視窗中，沒有可供您使用的布林運算式來篩選內容篩選器控制項。 Enter`localA[localIdx[0]] > 20000`在篩選控制項文字方塊方塊，然後選擇  **Enter**索引鍵。

   此視窗現在包含只在其上的執行緒`localA[localIdx[0]]`值是否大於 20000。 內容仍會依照`localA[localIdx[0]]`資料行，也就是您稍早執行的排序動作。

## <a name="flagging-gpu-threads"></a>GPU 執行緒加上旗標

您可以藉由在加上旗標標示特定的 GPU 執行緒**GPU 執行緒** 視窗中，**平行監看式**視窗中或在資料提示方塊**平行堆疊**視窗。 如果 [GPU 執行緒] 視窗中的資料列包含一個以上的執行緒，該資料列加上旗標加上旗標的資料列中包含的所有執行緒。

### <a name="to-flag-gpu-threads"></a>GPU 執行緒加上旗標

1. 選取 [ **[執行緒]** 中的資料行標頭**平行監看式 1**排序依據] 圖格索引和執行緒索引視窗。

2. 在功能表列上選擇 [**偵錯** > **繼續**，因而導致四個執行緒，是作用中，以進行下一步] 屏障 （定義在 AMPMapReduce.cpp 一行 32）。

3. 選擇包含四個執行緒，現在是作用中的資料列左側的旗標符號。

   下圖顯示在四個作用中已標幟的執行緒**GPU 執行緒**視窗。

   ![已標幟的執行緒，[GPU 執行緒] 視窗](../../parallel/amp/media/campg.png "已標幟的執行緒，[GPU 執行緒] 視窗") <br/>
   [GPU 執行緒] 視窗中正在活動的執行緒

   **平行監看式** 視窗和的 DataTip**平行堆疊**這兩個視窗指出已標幟的執行緒。

4. 如果您想要專注於您加上旗標的四個執行緒，您可以選擇顯示，請在**GPU 執行緒**，**平行監看式**，並**平行堆疊**windows 中，只加上旗標執行緒。

   選擇**僅顯示已標幟**上任何的按鈕之 windows 或在**偵錯位置**工具列。 如下圖所示**僅顯示已標幟**按鈕**偵錯位置**工具列。

   ![偵錯位置工具列，以僅顯示已標幟的圖示](../../parallel/amp/media/camph.png "偵錯位置工具列，以僅顯示已標幟的圖示") <br/>
   **標示為僅顯示**按鈕

   現在**GPU 執行緒**，**平行監看式**，並**平行堆疊**視窗會顯示已標幟的執行緒。

## <a name="freezing-and-thawing-gpu-threads"></a>凍結和解除凍結 GPU 執行緒

您可以凍結 （暫止） 和解除凍結 （繼續） GPU 執行緒從**GPU 執行緒** 視窗或**平行監看式**視窗。 您可以凍結和解除凍結 CPU 執行緒相同的方式;如需資訊，請參閱[如何： 使用執行緒視窗](/visualstudio/debugger/how-to-use-the-threads-window)。

### <a name="to-freeze-and-thaw-gpu-threads"></a>若要凍結和解除凍結 GPU 執行緒

1. 選擇**僅顯示已標幟** 按鈕以顯示所有執行緒。

2. 在功能表列上選擇 **偵錯** > **繼續**。

3. 開啟 作用中的資料列的捷徑功能表，然後選擇**凍結**。

   下列圖例**GPU 執行緒**視窗會顯示所有的四個執行緒已遭到凍結。

   ![GPU 執行緒 視窗顯示已凍結的執行緒](../../parallel/amp/media/campk.png "GPU 執行緒 視窗顯示已凍結的執行緒") <br/>
   凍結執行緒**GPU 執行緒**視窗

   同樣地，**平行監看式**視窗會顯示所有的四個執行緒已遭到凍結。

4. 在功能表列上選擇 **偵錯** > **繼續**以便接下來四個 GPU 執行緒超過在第 22 行屏障進度，並連線到第 30 行的中斷點。 **GPU 執行緒**視窗會顯示四個先前已凍結的執行緒，仍會凍結並處於作用中狀態。

5. 在功能表列上選擇 **偵錯**，**繼續**。

6. 從**平行監看式** 視窗中，您可以個別或多個 GPU 執行緒也解除凍結。

### <a name="to-group-gpu-threads"></a>若要群組的 GPU 執行緒

1. 其中一個執行緒中的捷徑功能表上**GPU 執行緒** 視窗中，選擇**Group By**，**位址**。

   中的執行緒**GPU 執行緒**視窗會依位址。 位址會對應至每個執行緒群組所在的反組譯碼中的指示。 24 執行緒位於第 22 行何處[tile_barrier:: wait 方法](reference/tile-barrier-class.md#wait)執行。 12 執行緒是在行 32 屏障的指示。 這些執行緒的四個標示。 8 個執行緒位於第 30 行的中斷點。 這些執行緒的四個已凍結。 下圖顯示在群組的執行緒**GPU 執行緒**視窗。

   ![依位址分組的 GPU 執行緒 視窗中的執行緒](../../parallel/amp/media/campl.png "與執行緒的 [GPU 執行緒] 視窗會依位址") <br/>
   群組中的執行緒**GPU 執行緒**視窗

2. 您也可以執行**Group By**藉由開啟的資料格的捷徑功能表的作業**平行監看式**視窗中，選擇**Group By**，然後選擇  功能表項目，其對應於您要群組執行緒的方式。

## <a name="running-all-threads-to-a-specific-location-in-code"></a>執行程式碼中的特定位置的所有執行緒

在指定的圖格執行所有執行緒使用包含游標的那一行**都執行目前磚至游標處**。

### <a name="to-run-all-threads-to-the-location-marked-by-the-cursor"></a>執行至資料指標所標記的位置的所有執行緒

1. 在已凍結的執行緒的捷徑功能表，選擇**解除凍結**。

2. 在 **程式碼編輯器**，將游標放在第 30 行中。

3. 上的捷徑功能表**程式碼編輯器**，選擇**執行目前磚至游標處**。

   24 先前遭到封鎖而在第 21 行在屏障的執行緒已進入列 32。 這會顯示**GPU 執行緒**視窗。

## <a name="see-also"></a>另請參閱

[C++ AMP 概觀](../../parallel/amp/cpp-amp-overview.md)<br/>
[偵錯 GPU 程式碼](/visualstudio/debugger/debugging-gpu-code)<br/>
[如何：使用 GPU 執行緒視窗](/visualstudio/debugger/how-to-use-the-gpu-threads-window)<br/>
[如何：使用平行監看式視窗](/visualstudio/debugger/how-to-use-the-parallel-watch-window)<br/>
[使用並行視覺化檢視分析 c + + AMP 程式碼](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/03/09/analyzing-c-amp-code-with-the-concurrency-visualizer/)
