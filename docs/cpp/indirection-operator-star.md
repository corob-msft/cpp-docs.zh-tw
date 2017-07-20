---
title: "間接取值運算子：* | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "* 運算子"
  - "間接取值運算子"
  - "間接取值運算子, 語法"
  - "運算子 [C++], 間接取值 (Indirection)"
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 間接取值運算子：*
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 語法  
  
```  
  
* cast-expression  
```  
  
## 備註  
 一元間接運算子 \(**\***\) 會取值指標；也就是會將指標值轉換為左值。  間接運算子的運算元必須是類型指標。  間接運算式的結果是類型，指標類型即衍生自此。  在此內容中使用 **\*** 運算子與使用該運算子為二元運算子不同，後者是乘法。  
  
 如果運算元指向某個函式，則結果為函式指示項。  如果運算元指向某個儲存位置，則結果為指定儲存位置的左值。  
  
 間接運算子可以累計用於將指標取值成為指標。  例如：  
  
```  
// expre_Indirection_Operator.cpp  
// compile with: /EHsc  
// Demonstrate indirection operator  
#include <iostream>  
using namespace std;  
int main() {  
   int n = 5;  
   int *pn = &n;  
   int **ppn = &pn;  
  
   cout  << "Value of n:\n"  
         << "direct value: " << n << endl  
         << "indirect value: " << *pn << endl  
         << "doubly indirect value: " << **ppn << endl  
         << "address of n: " << pn << endl  
         << "address of n via indirection: " << *ppn << endl;  
}  
```  
  
 如果指標值無效，則結果會是未定義的。  下列清單包含最常見的一些使指標值無效的情況。  
  
-   指標是一個 null 指標。  
  
-   指標指定了在參考時不可見的本機項目位址。  
  
-   指標指定的位址與物件指向的類型並不一致。  
  
-   指標指定了執行中程式未使用的位址。  
  
## 請參閱  
 [具有一元運算子的運算式](../cpp/expressions-with-unary-operators.md)   
 [C\+\+ 運算子](../misc/cpp-operators.md)   
 [C\+\+ 運算子、優先順序和順序關聯性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [傳址運算子：&](../cpp/address-of-operator-amp.md)   
 [間接取值和傳址運算子](../c-language/indirection-and-address-of-operators.md)