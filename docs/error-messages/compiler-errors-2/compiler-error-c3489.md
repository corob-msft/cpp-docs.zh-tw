---
title: "編譯器錯誤 C3489 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3489
dev_langs:
- C++
helpviewer_keywords:
- C3489
ms.assetid: 47b58d69-459d-4499-abc7-5f0b9303d773
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: dd21e87beb83169e9ee827ad36903ac61d624ae3
ms.contentlocale: zh-tw
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3489"></a>編譯器錯誤 C3489
預設擷取模式為傳值方式時需要 'var'  
  
 當您指定 Lambda 運算式的預設擷取模式是透過傳值方式時，無法透過傳值方式將變數傳遞給該運算式的 Capture 子句。  
  
### <a name="to-correct-this-error"></a>更正這個錯誤  
  
-   不要將變數明確地傳遞給 Capture 子句，或  
  
-   不要透過傳值方式指定為預設擷取模式，或  
  
-   透過傳址方式指定為預設擷取模式，或  
  
-   透過傳址方式將變數傳遞給 Capture 子句 (這可能會變更 Lambda 運算式的行為)。  
  
## <a name="example"></a>範例  
 下列範例會產生 C3489，因為變數 `n` 是透過傳值方式出現在其預設模式為透過傳值方式之 Lambda 運算式的 Capture 子句中：  
  
```  
// C3489a.cpp  
  
int main()  
{  
   int n = 5;  
   [=, n]() { return n; } (); // C3489  
}  
```  
  
## <a name="example"></a>範例  
 下列範例顯示 C3489 的四種可能解決方式：  
  
```  
// C3489b.cpp  
  
int main()  
{  
   int n = 5;  
  
   // Possible resolution 1:  
   // Do not explicitly pass n to the capture clause.  
   [=]() { return n; } ();  
  
   // Possible resolution 2:  
   // Do not specify by-value as the default capture mode.  
   [n]() { return n; } ();  
  
   // Possible resolution 3:  
   // Specify by-reference as the default capture mode.  
   [&, n]() { return n; } ();  
  
   // Possible resolution 4:  
   // Pass n by reference to the capture clause.  
   [&n]() { return n; } ();  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [Lambda 運算式](../../cpp/lambda-expressions-in-cpp.md)