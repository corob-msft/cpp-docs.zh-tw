---
title: "編譯器錯誤 C2797 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 5eea0aae37627015f8723835e4e3e1cb0c6d2e94
ms.contentlocale: zh-tw
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-error-c2797"></a>編譯器錯誤 C2797
（已過時）未實作成員初始設定式清單或非靜態資料成員初始設定式清單初始化。  
  
 這項警告是在 Visual Studio 2015 中已過時。 在 Visual Studio 2013 和舊版中，Visual c + + 編譯器未實作成員初始設定式清單或非靜態資料成員初始設定式清單初始化。 在 Visual Studio 2013 Update 3 之前，這會以無訊息模式轉換成函式呼叫，這樣可能會導致產生錯誤的程式碼。 Visual Studio 2013 Update 3 將此報告為錯誤。  
  
 本範例會產生 C2797：  
  
```  
#include <vector>  
struct S {  
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'  
  
    std::vector<int> v1;  
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'  
};  
  
```  
  
 本範例也會產生 C2797：  
  
```  
struct S1 {  
    int i;  
};  
  
struct S2 {  
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664  
    S1 s1;  
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664  
};  
  
```  
  
 若要修正這個問題，您可以使用內部清單的明確建構。 例如：  
  
```  
#include <vector>  
typedef std::vector<int> Vector;  
struct S {  
    S() : v1(Vector{1}) {}  
  
    Vector v1;  
    Vector v2 = Vector{1, 2};  
};  
  
```  
  
 如果您不需要清單初始設定：  
  
```  
struct S {  
    S() : s1("") {}  
  
    std::string s1;  
    std::string s2 = std::string("");  
};  
  
```  
  
 (Visual Studio 2013 中的編譯器會在 Visual Studio 2013 Update 3 之前隱含地執行此操作。)