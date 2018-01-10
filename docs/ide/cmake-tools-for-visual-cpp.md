---
title: "CMake 專案中 Visual c + + |Microsoft 文件"
ms.custom: 
ms.date: 08/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d38538ce929410782eee7a0a6540bb62a05b7669
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="cmake-projects-in-visual-c"></a>CMake 專案中 Visual c + +
本文假設您熟悉 CMake，用於定義多個平台執行的建置流程中的跨平台、 開放原始碼工具。  

直到最近，Visual Studio 使用者可以使用 CMake 產生 MSBuild 專案檔，然後在 IDE 所耗用的 IntelliSense，瀏覽和編譯。 從 Visual Studio 2017， **CMake 的 Visual c + + 工具**元件用 「 開啟資料夾 」 功能來啟用 IDE，才能使用 CMake 專案檔 （例如 CMakeLists.txt) 直接進行 IntelliSense 和瀏覽。 如果您使用 Visual Studio 產生器時，暫時專案檔產生和傳遞至 msbuild.exe，但永遠不會載入 IntelliSense 或瀏覽之用。 

**Visual Studio 2017 版本 15.3**： 為忍者和 Visual Studio 產生器提供的支援。

**Visual Studio 2017 版本 15.4**: Linux 上 CMake 加入支援。 如需詳細資訊，請參閱[設定 Linux CMake 專案](../linux/cmake-linux-project.md)。

## <a name="installing"></a>安裝
CMake 的 visual c + + 工具會安裝預設值做為桌面的 c + + 工作負載開發的一部分。

![CMake c + + 桌面的工作負載中的元件](media/cmake-install.png)
 
## <a name="ide-integration"></a>IDE 整合
當您選擇**檔案 |開啟 |資料夾**會開啟包含 CMakeLists.txt 檔案的資料夾，發生下列情況：
- Visual Studio 會加入**CMake**主功能表中，以檢視和編輯 CMake 指令碼命令的功能表項目。 
- **方案總管 中**顯示的資料夾結構和檔案。 
- Visual Studio 執行 CMake.exe 並產生預設的 CMake 快取*組態*，即 x86 偵錯。 CMake 命令列會顯示在**輸出 視窗**，以及從 CMake 其他輸出。
- 在背景中，Visual Studio 會啟動啟用 IntelliSense、 瀏覽資訊、 重構，來源檔案編製索引等。 工作時，Visual Studio 就會監視在編輯器中，保持它的索引與來源同步的磁碟上的變更。 您可以開啟包含任意數目的 CMake 專案資料夾。 Visual Studio 會偵測，並設定工作區中的所有 「 根 」 CMakeLists.txt 檔案。 CMake 作業 （設定、 建置、 偵錯），以及 c + + IntelliSense 和瀏覽可用的工作區中的所有 CMake 專案。

![具有多個根 CMake 專案](media/cmake-multiple-roots.png) 

## <a name="building-cmake-projects"></a>建置 CMake 專案
若要建置 CMake 專案，您有這些選項：
1. 在偵錯下拉式清單中，然後按選取目標**F5**或按一下 [執行] 按鈕。 專案會自動建置第一次，就像使用 Visual Studio 方案。
2.  以滑鼠右鍵按一下 CMakeLists.txt 並從內容功能表中選取的組建。 如果您有多個目標資料夾結構中，您可以選擇建立所有或只有一個特定目標，或
  
3. 從主功能表中，選取**建置 |建置方案**(**F7**或**Ctrl + Shift + B**) (請確定已在選取 CMake 目標**啟動項目**下拉式清單中**一般**工具列)。

![CMake 建置 功能表命令](media/cmake-build-menu.png) 
 
選取 Visual Studio 產生器時，使用中組態，以叫用 MSBuild.exe`-m -v:minimal`引數。 若要自訂的組建，CMakeSettings.json，檔案內部，您可以指定其他命令列引數傳遞至建置系統，透過`buildCommandArgs`屬性：

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```
如您所預期，組建結果會顯示在**輸出 視窗**和**錯誤清單**。
 
![CMake 建置錯誤](media/cmake-build-errors.png)

在具有多個建置目標的資料夾，您可以選擇 CMake 功能表或 CMakeLists.txt 操作功能表，來指定要建置哪個 CMake 目標組建項目。 按下**Ctrl + Shift + B** CMake 在專案建置目前現用的文件。 

## <a name="debugging-the-project"></a>偵錯專案
若要偵錯 CMake 專案，選擇所需的組態，然後按**F5**，或在工具列中按 [執行] 按鈕。 如果 [執行] 按鈕會顯示 「 選擇啟動項目 」，按一下向下箭號，然後選擇您想要執行的目標。 (在 CMake 專案中，「 目前文件 」 選項才有效的.cpp 檔案。) 

 ![執行 CMake 按鈕](media/cmake-run-button.png)

 按下**F5**一個組建之後所做的變更是否會第一次建置專案。

## <a name="configuring-cmake-debugging-sessions"></a>設定 CMake 偵錯工作階段
在一般的工具列上的啟動項目下拉式清單中，會顯示所有可執行 CMake 目標。 若要啟動偵錯工作階段，只要選取其中一個，然後啟動偵錯工具。

 ![CMake 啟動項目下拉式清單](media/cmake-startup-item-dropdown.png)

您也可以從 CMake 功能表啟動偵錯工作階段。

若要自訂您的專案中任何可執行 CMake 目標的偵錯工具設定，以滑鼠右鍵按一下特定 CMakeLists.txt 檔案，然後選取**偵錯和啟動設定**，當您在子功能表中，名為的檔案選取 CMake 目標建立 launch.vs.json。 這個檔案已預先填入您所選取的 CMake 目標的相關資訊，可讓您指定其他參數，例如程式引數或偵錯工具類型。 若要參考 CMakeSettings.json 檔案中的任何索引鍵，前面上它與"cmake。 」 在 launch.vs.json。 下列範例顯示簡單 launch.vs.json 檔案提取 CMakeSettings.json 目前選取的組態檔中的"remoteCopySources"索引鍵的值：

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
   {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```
只要儲存 launch.vs.json 檔案時，項目會建立具有新名稱的啟動項目下拉式清單中。 藉由編輯 launch.vs.json 檔案，您可以建立許多偵錯組態，為任意數目的 CMake 目標。

**Visual Studio 2017 版本 15.4**: Launch.vs.json 支援宣告的變數中 CMakeSettings.json （請參閱下文）。 它也會有"currentDir 」，此值會設定為啟動應用程式的目前目錄的概念：

```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```
當您執行應用程式時，值`currentDir`是 

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```
 

## <a name="editing-cmakeliststxt-files"></a>編輯 CMakeLists.txt 檔案
若要編輯 CMakeLists.txt 檔案，以滑鼠右鍵按一下中的檔案**方案總管 中**選擇**開啟**。 若要變更檔案，黃色狀態列會出現，並會通知您，IntelliSense 會更新，而讓您有機會取消更新作業。 如需 CMakeLists.txt 資訊，請參閱[CMake 文件](https://cmake.org/documentation/)。

  ![CMakeLists.txt 檔案編輯](media/cmake-cmakelists.png)

一旦您儲存檔案時，組態步驟會自動再次執行，並在 [輸出] 視窗中顯示資訊。 錯誤和警告會顯示錯誤清單或輸出視窗中。 按兩下 錯誤清單，以瀏覽至 CMakeLists.txt 中有問題的那一行中的錯誤。

  ![CMakeLists.txt 檔案錯誤](media/cmake-cmakelists-error.png)
 
## <a name="cmake_settings"></a>CMake 設定和自訂設定
根據預設，Visual Studio 會提供六個預設 CMake 設定 （x86 偵錯、 x86 發行、 x64 偵錯、 x64-發行 」、 「 Linux 偵錯 」 和 「 Linux 發行 」）。 這些設定會定義如何 CMake.exe 會叫用來建立針對指定的專案 CMake 快取。 若要修改這些設定，或建立新的自訂組態，選擇**CMake |變更 CMake 設定**，然後選擇的設定會套用至 CMakeLists.txt 檔案。 變更 CMake 設定也會提供檔案的內容功能表上**方案總管 中**。 此命令會建立 CMakeSettings.json 檔案的專案資料夾中。 這個檔案用來重新建立 CMake 快取檔案，例如 「 乾淨的 」 作業之後。 

  ![變更設定的 CMake 主功能表命令](media/cmake-change-settings.png)
 
JSON IntelliSense 可協助您編輯 CMakeSettings.json 檔案：

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png)

下列範例顯示範例組態中，您可以使用做為起點來建立您自己 CMakeSettings.json 中：
```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```
1.  名稱： 會出現在 c + + 的組態下拉式清單中的名稱。 這個屬性值也可用為巨集`${name}`來指定其他屬性值。 如需範例，請參閱 CMakeSettings.json"buildRoot"定義。
2.  產生器： 對應至-G 選項，並指定要使用產生器。 這個屬性也可用為巨集`${generator}`可協助您指定其他屬性值。 Visual Studio 目前支援下列 CMake 產生器：
    - 「 忍者 」
    - [Visual Studio 14 2015]
    - 「 Visual Studio 14 2015 部門 」
    - 「 Visual Studio 14 2015 Win64"
    - [Visual Studio 15 2017年]
    - 「 Visual Studio 15 2017年部門 」
    - 「 Visual Studio 15 2017 Win64"
    - 
因為忍者可供快速建置速度，而不是大的彈性和函式，它會設定為預設值。 不過，有些 CMake 專案可能無法正確建置使用忍者一樣。 如果發生這種情況，您可以指示 CMake 改為產生的 Visual Studio 專案。 

若要指定 Visual Studio 產生器中，開啟 CMakeSettings.json 從主要功能表選擇**CMake |變更 CMake 設定**。 刪除"忍者 」，並輸入"V"。 這會啟用 IntelliSense，可讓您選擇您想要的產生器。
3.  buildRoot： 對應至-DCMAKE_BINARY_DIR 交換器，並指定 CMake 快取建立的位置。 如果資料夾不存在，則會建立。
4.  變數： 包含 CMake 變數，會取得傳遞給-Dname 為名稱 + 值組 = CMake 的值。 如果您 CMake 專案組建的指示指定直接 CMake 快取檔案中加入的任何變數，則建議，您在此處加入改為。
5.  cmakeCommandArgs： 指定您想要傳遞給 CMake.exe 任何其他參數。
6.  組態類型： 定義所選的產生器的組建組態類型。 目前支援的值為"Debug"、"MinSizeRel 」、 「 發行 」 和 「 RelWithDebInfo"。

### <a name="environment-variables"></a>環境變數
CMakeSettings.json 也支援使用環境變數，在任何先前所述的屬性。 若要使用的語法是`${env.FOO}`展開環境變數 %FOO%。
您還必須存取內建的巨集，在此檔案：
- `${workspaceRoot}`– 提供工作區資料夾的完整路徑
- `${workspaceHash}`– 工作區的位置，雜湊適用於建立目前的工作區 （例如，資料夾路徑中使用） 的唯一識別碼
- `${projectFile}`– 根 CMakeLists.txt 檔案的完整路徑
- `${projectDir}`– 根 CMakeLists.txt 檔案的資料夾的完整路徑
- `${thisFile}`– CMakeSettings.json 檔案的完整路徑
- `${name}`– 組態的名稱
- `${generator}`– 此組態中使用 CMake 產生器的名稱

### <a name="ninja-command-line-arguments"></a>忍者一樣命令列引數

如果未指定目標，就會建置 'default' 目標 （請參閱手動）。

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|選項|描述|  
|--------------|------------|  
| -版本  | 列印忍者版本 ("1.7.1")| 
|   -C DIR   | 將變更為 DIR 再進行其他動作| 
|   -f 檔案  | 指定輸入的組建檔案 [default=build.ninja]| 
|   -j N     | 以平行方式執行 N 作業 [預設值 = 14 中，衍生自可用的 Cpu]| 
|   -k N     | N 則工作失敗，直到 [預設值 = 1]| 
|   -l N     | 不會啟動新的工作負載平均大於 N| 
|   -n      | 乾執行 （不執行命令，但作用如同成功）| 
|   -v       | 顯示所有的命令列建置時| 
|   -d 模式  | 啟用偵錯 （使用-d 清單加入至清單模式）| 
|   -t 工具  | 執行 subtool （使用-t 清單加入至清單子工具）。 終止 toplevel 選項。進一步將旗標傳遞至工具| 
|   -w 旗標  | 調整警告 （使用-w 清單加入至清單警告）| 


### <a name="inherited-environments-visual-studio-2017-version-155"></a>繼承的環境 (Visual Studio 2017 15.5 版本)

CmakeSettings.json 現在支援 inherted 環境。 這項功能可讓您建立自訂變數：

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

此欄位會設定執行時都會自動傳遞至 CMake.exe 的變數。 上述範例相當於執行 「 開發人員命令提示字元 VS 2017"與`-arch=amd64 -host_arch=amd64`引數。

下表顯示支援的值和其命令列的對等項目：

|內容名稱|描述|  
|-----------|-----------------|
|vsdev|預設的 Visual Studio 環境|
|msvc_x86|適用於 x86 使用 x86 編譯工具|
|msvc_arm| 使用 x86 arm 編譯工具|
|msvc_arm64|使用 x86 ARM64 針對編譯工具|
|msvc_x86_x64|使用 x86 AMD64 針對編譯工具|
|msvc_x64_x64|使用 64 位元工具針對 AMD64 編譯|
|msvc_arm_x64|為 ARM 使用 64 位元工具進行編譯|
|msvc_arm64_x64|使用 64 位元工具針對 ARM64 編譯|


重大變更時 CMakeSettings.json 或 CMakeLists.txt 檔案，Visual Studio 會自動重新執行 CMake 設定步驟。 如果沒有錯誤，完成設定步驟，所收集的資訊會提供 c + + IntelliSense 和語言服務以及在組建中並偵錯作業。

當多個 CMake 專案會使用相同的 CMake 組態名稱 （例如，x86-偵錯） 時，全部都設定和建置 （自己組建根資料夾中） 時選取該組態。 您可以偵錯來自所有參與該 CMake 組態 CMake 專案目標。

   ![CMake 只建立功能表項目](media/cmake-build-only.png)

若要限制的組建和偵錯工作階段，以在工作區中專案的子集，CMakeSettings.json 檔案的唯一名稱建立新的組態，並將它套用到僅限這些專案。 該組態時選取，IntelliSense，建置，而且將會啟用偵錯，只會針對所指定的專案。

## <a name="troubleshooting-cmake-cache-errors"></a>CMake 快取錯誤疑難排解
如果您需要 CMake 快取來診斷問題的狀態相關的詳細資訊，請開啟 CMake 主功能表或 CMakeLists.txt 內容功能表中的**方案總管 中**執行其中一個命令：
- **檢視快取**組建根資料夾中，在編輯器中開啟 CMakeCache.txt 檔案。 （如果您清除快取，CMakeCache.txt 至您所做的任何編輯會抹除。 若要進行保存之後會清除快取的變更，請參閱[CMake 設定和自訂設定](#cmake_settings)這篇文章中稍早。)
- **開啟快取資料夾**組建根資料夾檔案總管 視窗隨即開啟。  
- **清除快取**，好讓下一步 CMake 設定步驟開始從全新的快取刪除組建根資料夾。
- **產生快取**會強制產生步驟，以執行即使 Visual Studio 會考慮環境保持最新狀態。
