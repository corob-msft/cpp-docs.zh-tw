---
title: "間接取值和傳址運算子 | Microsoft Docs"
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
  - "& 運算子, 傳址運算子"
  - "* 運算子"
  - "* 運算子, 傳址運算子"
  - "* 運算子, 間接取值運算子"
  - "位址 [C++]"
  - "位址 [C++], 間接取值 (Indirection)"
  - "傳址運算子 (&)"
  - "Ampersand 運算子 (&)"
  - "間接取值運算子"
  - "null 指標 [C++]"
  - "運算子 [C++], 傳址"
  - "運算子 [C++], 間接取值 (Indirection)"
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 間接取值和傳址運算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

間接運算子 \(**\***\) 會透過指標間接存取值。  運算元必須是指標值。  運算的結果為由運算元定址的值，即其運算元指向位址的值。  結果的類型是運算元所定址的類型。  
  
 如果運算元指向某個函式，則結果為函式指示項。  如果運算元指向某個儲存位置，則結果為指定儲存位置的左值。  
  
 如果指標值無效，則結果會是未定義的。  下列清單包含最常見的一些使指標值無效的情況。  
  
-   指標是一個 null 指標。  
  
-   指標指定了在參考時不可見的本機項目位址。  
  
-   指標指定的位址與物件指向的類型並不一致。  
  
-   指標指定了執行中程式未使用的位址。  
  
 傳址運算子 \(**&**\) 會提供其運算元的位址。  傳址運算子的運算元可以是函式指示項或左值，此左值指定的物件不是位元欄位，並且不使用 **register** 儲存類別規範宣告。  
  
 位址運算的結果為指向運算元的指標。  由指標定址的類型即是運算元的類型。  
  
 傳址運算子僅適用於在檔案範圍層級宣告基本、結構或等位類型的變數，或是註標的陣列參考。  在這些運算式中，未包含傳址運算子的常數運算式可以在位址運算式中進行加法或減法運算。  
  
## 範例  
 下列是使用這些宣告的範例：  
  
```  
int *pa, x;  
int a[20];  
double d;  
```  
  
 這個陳述式使用傳址運算子：  
  
```  
pa = &a[5];  
```  
  
 傳址運算子 \(**&**\) 會取得陣列 `a` 第六個元素的位址。  結果會儲存在指標變數 `pa` 中。  
  
```  
x = *pa;  
```  
  
 此例中使用間接取值運算子 \(**\***\) 來存取儲存在 `pa` 中位址的 `int` 值。  此值已指派給整數變數 `x`。  
  
```  
if( x == *&x )  
    printf( "True\n" );  
```  
  
 此範例會列印文字 `True`，示範對 `x` 位址套用間接取值運算子的結果與 `x` 相同。  
  
```  
int roundup( void );     /* Function declaration */  
  
int  *proundup  = roundup;  
int  *pround  = &roundup;  
```  
  
 宣告 `roundup` 函式後，就會宣告及初始化 `roundup` 的兩個指標。  第一個指標 \(`proundup`\) 只使用函式的名稱初始化，而第二個指標 \(`pround`\) 則在初始化時使用傳址運算子。  兩個初始化相同。  
  
## 請參閱  
 [間接取值運算子：\*](../cpp/indirection-operator-star.md)   
 [傳址運算子：&](../cpp/address-of-operator-amp.md)