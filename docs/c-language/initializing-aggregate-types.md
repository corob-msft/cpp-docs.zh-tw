---
title: "初始化彙總類型 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "彙總類型 [C++]"
  - "彙總 [C++], 初始化"
  - "類型 [C], 初始化"
  - "union 關鍵字 [C]"
  - "union 關鍵字 [C], 宣告"
ms.assetid: a8f8ed75-39db-4592-93b9-d3920d915810
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 初始化彙總類型
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

「彙總」類型是一種結構、等位或陣列類型。  如果彙總類型包含彙總類型的成員，則會以遞迴方式套用初始化規則。  
  
## 語法  
 *initializer*:  
 **{**  *initializer\-list*  **}** \/\* 適用彙總初始化 \*\/  
  
 **{**  *initializer\-list*  **, }**  
  
 *initializer\-list*:  
 *initializer*  
  
 *initializer\-list*  **,**  *initializer*  
  
 *initializer\-list* 是以逗號分隔的初始設定式清單。  清單中的每個初始設定式不是常數運算式就是初始設定式清單。  因此，初始設定式清單可以是巢狀。  這個表單在初始化彙總類型的彙總成員時很有用，如本節中的範例所示。  不過，如果自動識別項的初始設定式是單一運算式，則它不一定要是常數運算式，只需要具有適當的類型可指派給識別項即可。  
  
 對於每個初始設定式清單，常數運算式的值都會依序指派給對應的彙總變數成員。  
  
 如果 *initializer\-list* 包含的值少於彙總類型，則彙總類型的其餘成員或項目都會初始化為 0。  未明確初始化的自動識別項初始值會是未定義。  如果 *initializer\-list* 包含的值多於彙總類型，則會產生錯誤。  這些規則適用於每個內嵌的初始設定式清單，同時適用於整個彙總。  
  
 結構的初始設定式會是相同類型的運算式，或是其成員以大括號括住的初始設定式清單 \(**{ }**\)。  未命名的位元欄位成員不會初始化。  
  
 初始化等位時，*initializer\-list* 必須是單一常數運算式。  常數運算式的值會指派給等位的第一個成員。  
  
 如果陣列的大小未知，則初始設定式的數目會決定陣列的大小，而且其類型會變成完整。  目前無法在未提供所有前述值的情況下，在 C 中指定初始設定式的重複項目，或是在陣列中初始化元素。  如果您的程式中需要這項作業，請用組合語言撰寫常式。  
  
 請注意，初始設定式的數目可能會設定陣列的大小：  
  
```  
int x[ ] = { 0, 1, 2 }  
```  
  
 如果您指定大小，但提供了不正確的初始設定式數目，編譯器就會產生錯誤。  
  
 **Microsoft 特定的**  
  
 陣列的大小上限是由 **size\_t** 所定義。  其定義在標頭檔 STDDEF.H 中，**size\_t** 是一個範圍從 0x00000000 到 0x7CFFFFFF 的 `unsigned int`。  
  
 **END Microsoft 特定的**  
  
## 範例  
 這個範例將示範陣列的初始設定式。  
  
```  
int P[4][3] =   
{  
    { 1, 1, 1 },  
    { 2, 2, 2 },  
    { 3, 3, 3,},  
    { 4, 4, 4,},  
};  
```  
  
 這個陳述式會將 `P` 宣告為 4 x 3 陣列，並且將陣列第一列的元素初始化為 1，第二列的元素初始化為 2，依此類推。  請注意，第三和第四列的初始設定式清單會在最後一個常數運算式之後包含逗號。  最後一個初始設定式清單 \(`{4, 4, 4,},`\) 後面也會接著逗號。  雖然可以使用這些額外的逗號，但並非必要，只有分隔各個常數運算式以及分隔各個初始設定式清單的逗號才是必要。  
  
 如果彙總成員沒有內嵌的初始設定式清單，則會直接將值依序指派給子彙總的每個成員。  因此，上述範例中的初始化相當於下面所列：  
  
```  
int P[4][3] =   
{  
   1, 1, 1, 2, 2, 2, 3, 3, 3, 4, 4, 4  
};  
```  
  
 括號也可以出現在清單中個別初始設定式的前後，這樣有助於釐清上面的範例。  
  
 當您初始化彙總變數時，必須注意括號和初始設定式清單的正確使用方式。  下列範例將詳細說明編譯器對括號的解譯：  
  
```  
typedef struct   
{  
    int n1, n2, n3;  
} triplet;  
  
triplet nlist[2][3] =   
{  
    { {  1, 2, 3 }, {  4, 5, 6 }, {  7, 8, 9 } },  /* Row 1 */  
    { { 10,11,12 }, { 13,14,15 }, { 16,17,18 } }   /* Row 2 */  
};  
```  
  
 在這個範例中，`nlist` 會宣告為 2 x 3 結構陣列，每個結構擁有三個成員。  第 1 列初始化會將值指派給 `nlist` 的第一列，如下所示：  
  
1.  第 1 列上的第一個左大括號會通知編譯器 `nlist` 第一個彙總成員 \(也就是 `nlist[0]`\) 的初始化開始。  
  
2.  第二個左大括號表示 `nlist[0]` 第一個彙總成員 \(也就是位於 `nlist[0][0]` 的結構\) 的初始化開始。  
  
3.  第一個右大括號表示結構 `nlist[0][0]` 的初始化結束，下一個左大括號表示 `nlist[0][1]` 的初始化開始。  
  
4.  這個程序會繼續進行到行尾，該處的右大括號表示 `nlist[0]` 的初始化結束。  
  
 第 2 列會以類似的方式將值指派給 `nlist` 的第二列。  請注意，第 1 和第 2 列上括住初始設定式外側的大括號為必要。  下列建構省略了外側大括號，這樣會產生錯誤：  
  
```  
triplet nlist[2][3] =  /* THIS CAUSES AN ERROR */  
{  
     {  1, 2, 3 },{  4, 5, 6 },{  7, 8, 9 },   /* Line 1 */  
     { 10,11,12 },{ 13,14,15 },{ 16,17,18 }    /* Line 2 */  
};  
```  
  
 在這個結構中，第 1 行的第一個左大括號表示 `nlist[0]` 的初始化開始，它是具有三個結構的陣列。  1、2 和 3 這三個值會指派給第一個結構的三個成員。  遇到下一個右大括號時 \(在數值 3 之後\)，`nlist[0]` 的初始化就會完成，而在三個結構陣列中的其餘兩個結構會自動初始化為 0。  同樣地，`{ 4,5,6 }` 會初始化 `nlist` 中第二列的第一個結構。  `nlist[1]` 的其餘兩個結構會設為 0。  當編譯器遇到下一個初始設定式清單 \(`{ 7,8,9 }` \) 時，會嘗試初始化 `nlist[2]`。  由於 `nlist` 只有兩列，因此這項嘗試會產生錯誤。  
  
 在下一個範例中，`x` 的三個 `int` 成員會分別初始化為 1、2 和 3。  
  
```  
struct list   
{  
    int i, j, k;  
    float m[2][3];  
} x = {  
        1,  
        2,  
        3,  
       {4.0, 4.0, 4.0}  
      };  
```  
  
 在上面的 `list` 結構中，`m` 的第一行中的三個元素會初始化為 4.0，而根據預設，`m` 的其餘列中的元素會初始化為 0.0。  
  
```  
union  
{  
    char x[2][3];  
    int i, j, k;  
} y = { {  
            {'1'},  
            {'4'}   
        }  
      };  
```  
  
 這個範例中的等位變數 `y` 會初始化。  等位的第一個項目是陣列，因此初始設定式是彙總初始設定式。  初始設定式清單 `{'1'}` 會將值指派給陣列的第一列。  由於清單中只有一個值，因此第一行中的元素會初始化為 `1` 字元，而根據預設，該列中的其餘兩個元素會初始化為 0 值。  同樣地，`x` 中第二列的第一個元素會初始化為 `4` 字元，該列中的其餘兩個元素則會初始化為 0 值。  
  
## 請參閱  
 [初始化](../c-language/initialization.md)