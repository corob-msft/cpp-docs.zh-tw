---
title: "tile_static 關鍵字 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "tile_static_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tile_static 關鍵字"
ms.assetid: d78384d4-65d9-45cf-b3df-7e904f489d06
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# tile_static 關鍵字
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`tile_static` 關鍵字用於宣告可供執行緒磚中所有執行緒存取的變數。  變數的存留期從執行達到宣告點時開始，並在核心函式傳回時結束。  如需使用磚塊的詳細資訊，請參閱[使用磚](../parallel/amp/using-tiles.md)。  
  
 `tile_static` 關鍵字具有下列限制：  
  
-   只能用於具有 `restrict(amp)` 修飾詞之函式中的變數。  
  
-   不可用於屬於指標或參考類型的變數。  
  
-   `tile_static` 變數不能有初始設定式。  不會自動叫用預設建構函式和解構函式。  
  
-   未初始化 `tile_static` 變數的值並未定義。  
  
-   如果在呼叫圖形中宣告 `tile_static` 變數，且該呼叫圖形是以對 `parallel_for_each` 的非磚式呼叫為根本，則會產生警告，並且該變數的行為未定義。  
  
## 範例  
 下列範例顯示如何使用 `tile_static` 變數跨磚狀顯示的數個執行緒累積資料。  
  
```cpp  
  
// Sample data:  
int sampledata[] = {  
    2, 2, 9, 7, 1, 4,  
    4, 4, 8, 8, 3, 4,  
    1, 5, 1, 2, 5, 2,  
    6, 8, 3, 2, 7, 2};  
  
// The tiles:  
// 2 2    9 7    1 4  
// 4 4    8 8    3 4  
//  
// 1 5    1 2    5 2  
// 6 8    3 2    7 2  
  
// Averages:  
int averagedata[] = {   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
};  
  
array_view<int, 2> sample(4, 6, sampledata);  
array_view<int, 2> average(4, 6, averagedata);  
  
parallel_for_each(  
    // Create threads for sample.extent and divide the extent into 2 x 2 tiles.  
    sample.extent.tile<2,2>(),  
    [=](tiled_index<2,2> idx) restrict(amp)  
    {  
        // Create a 2 x 2 array to hold the values in this tile.  
        tile_static int nums[2][2];  
        // Copy the values for the tile into the 2 x 2 array.  
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];  
        // When all the threads have executed and the 2 x 2 array is complete, find the average.  
        idx.barrier.wait();  
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];  
        // Copy the average into the array_view.  
        average[idx.global] = sum / 4;  
      }  
);  
  
for (int i = 0; i < 4; i++) {  
    for (int j = 0; j < 6; j++) {  
        std::cout << average(i,j) << " ";  
    }  
    std::cout << "\n";  
}  
  
// Output:  
// 3 3 8 8 3 3  
// 3 3 8 8 3 3  
// 5 5 2 2 4 4  
// 5 5 2 2 4 4  
// Sample data.  
int sampledata[] = {  
    2, 2, 9, 7, 1, 4,  
    4, 4, 8, 8, 3, 4,  
    1, 5, 1, 2, 5, 2,  
    6, 8, 3, 2, 7, 2};  
  
// The tiles are:  
// 2 2    9 7    1 4  
// 4 4    8 8    3 4  
//  
// 1 5    1 2    5 2  
// 6 8    3 2    7 2  
  
// Averages.  
int averagedata[] = {   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
    0, 0, 0, 0, 0, 0,   
};  
  
array_view<int, 2> sample(4, 6, sampledata);  
array_view<int, 2> average(4, 6, averagedata);  
  
parallel_for_each(  
    // Create threads for sample.grid and divide the grid into 2 x 2 tiles.  
    sample.extent.tile<2,2>(),  
    [=](tiled_index<2,2> idx) restrict(amp)  
    {  
        // Create a 2 x 2 array to hold the values in this tile.  
        tile_static int nums[2][2];  
        // Copy the values for the tile into the 2 x 2 array.  
        nums[idx.local[1]][idx.local[0]] = sample[idx.global];  
        // When all the threads have executed and the 2 x 2 array is complete, find the average.  
        idx.barrier.wait();  
        int sum = nums[0][0] + nums[0][1] + nums[1][0] + nums[1][1];  
        // Copy the average into the array_view.  
        average[idx.global] = sum / 4;  
      }  
);  
  
for (int i = 0; i < 4; i++) {  
    for (int j = 0; j < 6; j++) {  
        std::cout << average(i,j) << " ";  
    }  
    std::cout << "\n";  
}  
  
// Output.  
// 3 3 8 8 3 3  
// 3 3 8 8 3 3  
// 5 5 2 2 4 4  
// 5 5 2 2 4 4  
  
```  
  
## 請參閱  
 [Microsoft 專有的修飾詞](../cpp/microsoft-specific-modifiers.md)   
 [C\+\+ AMP 概觀](../parallel/amp/cpp-amp-overview.md)   
 [parallel\_for\_each 函式 \(C\+\+ AMP\)](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md)   
 [逐步解說：矩陣乘法](../parallel/amp/walkthrough-matrix-multiplication.md)