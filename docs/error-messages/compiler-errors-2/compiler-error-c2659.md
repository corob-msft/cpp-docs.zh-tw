---
title: "編譯器錯誤 C2659 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2659"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2659"
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 編譯器錯誤 C2659
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator' : 當做左運算元  
  
 函式在指定運算子的左邊。  這個錯誤最常見的原因是當開發人員要將運算子左方的識別項當做變數時，編譯器已將其剖析為函式。  如需詳細資訊，請參閱維基百科的文章：[最繁瑣的語法解析](http://en.wikipedia.org/wiki/Most_vexing_parse)。  此範例顯示容易混淆的函式宣告和變數定義：  
  
```  
// C2659a.cpp  
// Compile using: cl /W4 /EHsc C2659a.cpp  
#include <string>  
using namespace std;  
  
int main()   
{  
   string string1(); // string1 is a function returning string  
   string string2{}; // string2 is a string initialized to empty   
  
   string1 = "String 1"; // C2659  
   string2 = "String 2";  
}  
```  
  
 若要解決這個問題，請變更識別項的宣告，使其不會被解析為函式宣告。  
  
 當函式具有無法在指定運算子左方運算式中使用的類型時，也可能會發生錯誤 C2659。  此範例會在程式碼指派函式指標至函式時產生 C2659：  
  
```  
// C2659b.cpp  
// Compile using: cl /W4 /EHsc C2659b.cpp  
int func0(void) { return 42; }  
int (*func1)(void);  
  
int main()  
{  
   func1 = func0;  
   func0 = func1; // C2659  
}  
```