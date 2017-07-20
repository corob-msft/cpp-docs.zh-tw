---
title: "範圍規則摘要 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "類別名稱 [C++], 範圍規則"
  - "類別範圍 [C++], 規則"
  - "類別 [C++], 範圍"
  - "名稱 [C++], class"
  - "範圍 [C++], 類別名稱"
ms.assetid: 47e26482-0111-466f-b857-598c15d05105
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 範圍規則摘要
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

使用的名稱在其範圍內不可以模稜兩可 \(其位置由多載決定\)。  如果名稱表示一個函式，該函式必須明確指定參數的數目和類型。  如果名稱仍然模稜兩可，則會套用[成員存取](../cpp/member-access-control-cpp.md)規則。  
  
## 建構函式初始設定式  
 建構函式初始設定式 \(於[初始化基底和成員](http://msdn.microsoft.com/zh-tw/2f71377e-2b6b-49da-9a26-18e9b40226a1)中說明\) 會在所指定的建構函式最外層區塊的範圍內進行評估。  因此，它們可以使用建構函式的參數名稱。  
  
## 全域名稱  
 物件、函式或列舉程式若是在任何函式或類別之外引入，或是加上全域一元範圍運算子 \(`::`\) 前置詞，且未與下列任何二元運算子搭配使用，其名稱即為全域名稱：  
  
-   範圍解析 \(`::`\)  
  
-   物件和參考成員選取 \(**.**\)  
  
-   指標成員選取 \(**–\>**\)  
  
## 限定名稱  
 搭配二進位範圍解析運算子 \(`::`\) 使用的名稱亦稱為「限定名稱」\(Qualified Name\)。 在二進位範圍解析運算子後面指定的名稱，必須是運算子左方所指定類別的成員，或是其基底類別的成員。  
  
 成員選擇運算子 \(**.** 或 **–\>**\) 後面指定的名稱，必須是運算子左方所指定物件之類別類型的成員，或是其基底類別的成員。  假設成員選擇運算子 \(**–\>**\) 的左方是類別物件，且該類別定義的多載成員選擇運算子 \(**–\>**\) 會判斷值為其他類別類型的指標，則 **–\>** 右方指定的名稱也可以是另一個類別類型的物件   \(這項佈建將在[類別成員存取](../cpp/member-access.md)中詳細討論\)。  
  
 編譯器會依照下列順序搜尋名稱，並且在找到名稱時停止：  
  
1.  如果名稱是在函式內使用，則為目前區塊範圍，否則為全域範圍。  
  
2.  向外至每個封閉區塊範圍，包括最外層的函式範圍 \(包括函式參數\)。  
  
3.  如果名稱是在成員函式內使用，則會在類別的範圍內搜尋名稱。  
  
4.  在類別的基底類別內搜尋名稱。  
  
5.  在封閉巢狀類別範圍 \(如果有的話\) 及其基底內搜尋。  搜尋會繼續，直到搜尋至最外層封閉類別範圍為止。  
  
6.  在全域範圍內搜尋。  
  
 不過，您可以依照下述方式修改這個搜尋順序：  
  
1.  前面加上 `::` 的名稱會強制從全域範圍開始搜尋。  
  
2.  前面加上 **class**、`struct` 和 **union** 關鍵字的名稱會強制編譯器僅搜尋 **class**、`struct` 或 **union** 名稱。  
  
3.  範圍解析運算子 \(`::`\) 左邊的名稱只能是 **class**、`struct`、**namespace** 或 **union** 名稱。  
  
 如果名稱參考非靜態成員，但是在靜態成員函式中使用，則會產生錯誤訊息。  同樣地，如果名稱參考封閉式類別中的任何非靜態成員，也會產生錯誤訊息，因為已封閉的類別沒有封入類別 **this** 指標。  
  
## 函式參數名稱  
 函式定義中的函式參數名稱會視為在函式最外層區塊的範圍內。  因此，它們會是區域名稱且當函式結束時會超出範圍。  
  
 函式宣告 \(原型\) 中的函式參數名稱會位於宣告的區域範圍，而在宣告的結尾會超出範圍。  
  
 預設參數會位於其所預設的參數範圍內，如上兩個段落中所述。  但是，它們無法存取區域變數或非靜態類別成員。  預設參數是在函式呼叫時進行評估，但是它們是在函式宣告的原始範圍中進行評估。  因此，成員函式的預設參數一定是在類別範圍中進行評估。  
  
## 請參閱  
 [繼承](../cpp/inheritance-cpp.md)