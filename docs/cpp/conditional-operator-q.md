---
title: "條件運算子：? : | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "?:"
  - "?"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "? : 運算子"
  - "條件運算子"
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 條件運算子：? :
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 語法  
  
```  
  
expression ? expression : expression  
```  
  
## 備註  
 條件式運算子 \(**? :**\) 是一種三元運算子 \(它會採用三個運算元\)。  條件運算子運作方式如下：  
  
-   第一個運算元會隱含轉換成 `bool`。  接著會對它進行評估，並且完成所有副作用，再繼續執行。  
  
-   如果第一個運算元判斷值為 **true** \(1\)，就會評估第二個運算元。  
  
-   如果第一個運算元判斷值為 **false** \(0\)，則會評估第三個運算元。  
  
 條件運算子的結果會是所評估運算元 \(也就是第二個或第三個運算元\) 的結果。  在條件運算式中，只會評估後兩個運算元的其中一個。  
  
 條件運算式具有由右至左順序關聯性。  第一個運算元必須為整數類資料類型或指標類型。  下列規則適用於第二個和第三個運算元：  
  
-   如果這兩個運算元屬於相同類型，則結果為該類型。  
  
-   如果這兩個運算元為算術或列舉類型，則會進行一般算術轉換 \(涵蓋在[算術轉換](../misc/arithmetic-conversions.md)中\)，將它們轉換成一般類型。  
  
-   如果這兩個運算元都是指標類型，或者其中一個是指標類型，另一個是判斷值為 0 的常數運算式，則會進行指標轉換，將它們轉換成一般類型。  
  
-   如果這兩個運算元屬於參考類型，則會進行參考轉換，將它們轉換成一般類型。  
  
-   如果這兩個運算元屬於 void 類型，則一般類型會是 void 類型。  
  
-   如果這兩個運算元屬於相同的使用者定義類型，則一般類型會是該類型。  
  
-   如果運算元的類型不同，且至少其中一個運算元具有使用者定義類型，則會使用語言規則來判斷一般類型。  \(請參閱下列警告\)。  
  
 未包含在上述清單中的任何第二個和第三個運算元組合都不合法。  結果的類型是一般類型，而如果第二個和第三個運算元屬於相同類型且都是左值，則結果也會是左值。  
  
> [!WARNING]
>  如果第二個運算元的類型與第三個運算元的類型不同，則會叫用依照 C\+\+ 標準指定的複雜類型轉換規則。  這些轉換可能會導致非預期的行為，包括建構和解構暫存物件。  因此，強烈建議您 \(1\) 避免使用使用者定義類型做為搭配條件運算子的運算元，或者 \(2\) 如果您使用使用者定義類型，則明確地將每個運算元轉換成一般類型。  
  
## 範例  
  
```  
// expre_Expressions_with_the_Conditional_Operator.cpp  
// compile with: /EHsc  
// Demonstrate conditional operator  
#include <iostream>  
using namespace std;  
int main() {  
   int i = 1, j = 2;  
   cout << ( i > j ? i : j ) << " is greater." << endl;  
}  
```  
  
## 請參閱  
 [C\+\+ 運算子](../misc/cpp-operators.md)   
 [C\+\+ 運算子、優先順序和順序關聯性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [條件運算式運算子](../c-language/conditional-expression-operator.md)