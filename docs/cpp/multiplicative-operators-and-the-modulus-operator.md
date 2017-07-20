---
title: "乘法類運算子和模數運算子 | Microsoft Docs"
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
  - "%"
  - "/"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "% 運算子"
  - "* 運算子"
  - "算術運算子 [C++], 乘法運算子"
  - "除法運算子"
  - "除法運算子, 乘法運算子"
  - "模數運算子, C+"
  - "乘法運算子 [C++], 乘法運算子"
  - "乘法類運算子 [C++]"
  - "運算子 [C++], 乘法類"
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 乘法類運算子和模數運算子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 語法  
  
```  
expression * expression   
expression / expression   
expression % expression  
```  
  
## 備註  
 乘法類運算子包括：  
  
-   乘法 \(**\***\)  
  
-   除法 \(**\/**\)  
  
-   模數 \(除法的餘數\) \(`%`\)  
  
 這些二進位運算子具有由左至右的順序關聯性。  
  
 乘法類運算子接受算術類型的運算元。  模數運算子 \(`%`\) 具有較嚴格的要求，其運算元必須為整數類資料類型 \(若要取得浮點除法的餘數，請使用執行階段函式 [fmod](../c-runtime-library/reference/fmod-fmodf.md)\)。[算術轉換](../misc/arithmetic-conversions.md)中涵蓋的轉換適用於運算元，結果會是轉換後的類型。  
  
 乘法運算子會產生第一個運算元與第二個運算元相乘的結果。  
  
 除法運算子會產生第一個運算元除以第二個運算元的結果。  
  
 模數運算子會產生下列運算式所得出的餘數，其中 *e1* 是第一個運算元且 *e2* 是第二個運算元：*e1* – \(*e1* \/ *e2*\) \* *e2*，其中兩個運算元都是整數類資料類型。  
  
 在除法或模數運算式中除以 0 並未定義，而且會產生執行階段錯誤。  因此，下列運算式會產生未定義的錯誤結果：  
  
```  
i % 0  
f / 0.0  
```  
  
 如果乘法、除法或模數運算式的兩個運算元有相同的正負號，則結果為正數。  否則，結果為負數。  模數運算結果的正負號是由實作所定義。  
  
> [!NOTE]
>  由於乘法類運算子所執行的轉換不提供溢位或反向溢位條件，因此，如果乘法類運算的結果無法以轉換後的運算元類型表示，則資訊可能會遺失。  
  
## Microsoft 特定的  
 在 Microsoft C\+\+ 中，模數運算式的結果一律與第一個運算元的正負號相同。  
  
## END Microsoft 特定的  
 如果兩個整數計算的除法不精確，而且只有一個運算元為負數，則結果會是小於除法運算會產生之實際值的最大整數 \(範圍內，忽略正負號\)。  例如，–11 \/ 3 計算的值為 –3.666666666。  該整數除法的結果為 –3。  
  
 乘法類運算子之間的關聯性是由識別所指定 \(*e1* \/ *e2*\) \* *e2* \+ *e1* % *e2* \=\= *e1*。  
  
## 範例  
 下列程式將示範乘法類運算子。  請注意，`10 / 3` 的任一個運算元必須明確轉型為 `float` 類型避免發生截斷，如此在進行除法之前，兩個運算元都會是 `float` 類型。  
  
```  
// expre_Multiplicative_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main() {  
   int x = 3, y = 6, z = 10;  
   cout  << "3 * 6 is " << x * y << endl  
         << "6 / 3 is " << y / x << endl  
         << "10 % 3 is " << z % x << endl  
         << "10 / 3 is " << (float) z / x << endl;  
}  
```  
  
## 請參閱  
 [具有二元運算子的運算式](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ 運算子](../misc/cpp-operators.md)   
 [C\+\+ 運算子、優先順序和順序關聯性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 乘法類運算子](../c-language/c-multiplicative-operators.md)