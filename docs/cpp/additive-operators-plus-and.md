---
title: "加法類運算子：+ 和 - | Microsoft Docs"
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
  - "-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "- 運算子, C++ 中的加法類運算子"
  - "+ 運算子, 加法類運算子"
  - "加法類運算子"
  - "算術運算子 [C++], 加法類運算子"
  - "運算子 [C++], 加法"
  - "減法運算子, 加法類運算子"
ms.assetid: d4afafe7-e201-4c69-a649-37f17756e784
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 加法類運算子：+ 和 -
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 語法  
  
```  
expression + expression   
expression – expression  
```  
  
## 備註  
 加法類運算子為：  
  
-   加法 \(**\+**\)  
  
-   減法 \(**–**\)  
  
 這些二進位運算子具有由左至右的順序關聯性。  
  
 加法類運算子接受算術或指標類型運算元。  加法 \(**\+**\) 運算子的結果是運算元的總和。  減法 \(**–**\) 運算子的結果是運算元之間的差異。  如果一個或兩個運算元為指標，它們必須是物件的指標，而不是函式的指標。  如果兩個運算元都是指標，除非兩個運算元都是同一個陣列中的物件指標，否則結果並沒有意義。  
  
 加法類運算子接受 *arithmetic*、*integral* 及 *scalar* 類型的運算元。  其定義如下表所列。  
  
### 搭配加法類運算子使用的類型  
  
|類型|意義|  
|--------|--------|  
|*算術*|整數和浮點類型統稱為「算術」類型。|  
|*整數*|各種大小 \(long、short\) 的 char 和 int 及列舉是「整數」類型。|  
|*純量*|純量運算元是算術或指標類型的運算元。|  
  
 這些運算子的有效組合包括：  
  
 算術 \+ 算術  
  
 純量 \+ 整數  
  
 整數 \+ 純量  
  
 算術 – 算術  
  
 純量– 純量  
  
 請注意，加法和減法並非對等的運算。  
  
 如果兩個運算元都是算術類型，[算術轉換](../misc/arithmetic-conversions.md)中的轉換就適用於運算元，結果會是轉換後的類型。  
  
## 範例  
  
```  
// expre_Additive_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
#define SIZE 5  
using namespace std;  
int main() {  
   int i = 5, j = 10;  
   int n[SIZE] = { 0, 1, 2, 3, 4 };  
   cout  << "5 + 10 = " << i + j << endl  
         << "5 - 10 = " << i - j << endl;  
  
   // use pointer arithmetic on array  
  
   cout << "n[3] = " << *( n + 3 ) << endl;  
}  
```  
  
## 指標加法  
 如果其中一個加法運算的運算元是物件陣列的指標，其他運算元必須是整數類型。  結果會是與原始指標相同類型且指向另一個陣列元素的指標。  下列程式碼片段說明這個概念：  
  
```  
short IntArray[10]; // Objects of type short occupy 2 bytes  
short *pIntArray = IntArray;  
  
for( int i = 0; i < 10; ++i )  
{  
    *pIntArray = i;  
    cout << *pIntArray << "\n";  
    pIntArray = pIntArray + 1;  
}  
```  
  
 雖然已將整數值 1 加入至 `pIntArray`，但並不代表「對位址加 1」，而是表示「將指標調整為指向陣列中的下一個物件」，而其距離正好是 2 個位元組 \(或 `sizeof( int )`\)。  
  
> [!NOTE]
>  `pIntArray = pIntArray + 1` 形式的程式碼在 C\+\+ 程式中很少見，若要執行遞增作業，使用下列形式會更好：`pIntArray++` 或 `pIntArray += 1`。  
  
## 指標減法  
 如果兩個運算元都是指標，則減法運算的結果為兩個運算元之間的差數 \(以陣列元素為單位\)。  減法運算式會產生 ptrdiff\_t 類型的帶正負號整數結果 \(定義於標準的 Include 檔案 STDDEF.H 中\)。  
  
 兩個運算元中的第二個運算元可以是整數類資料類型。  減法運算的結果與原始指標的類型相同。  減法的值是第 \(*n* – *i*\) 個陣列元素的指標，其中 *n* 是原始指標所指向的元素，而 *i* 是第二個運算元的整數值。  
  
## 請參閱  
 [具有二元運算子的運算式](../cpp/expressions-with-binary-operators.md)   
 [C\+\+ 運算子](../misc/cpp-operators.md)   
 [C\+\+ 運算子、優先順序和順序關聯性](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [指標類型的加法運算](../misc/addition-of-pointer-types.md)   
 [指標類型的減法運算](../misc/subtraction-of-pointer-types.md)   
 [C 加法類運算子](../c-language/c-additive-operators.md)