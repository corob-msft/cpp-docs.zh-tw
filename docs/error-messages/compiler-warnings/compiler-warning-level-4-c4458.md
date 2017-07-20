---
title: "編譯器警告 （層級 4） C4458 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4458
dev_langs:
- C++
helpviewer_keywords:
- C4458
ms.assetid: 7bdaa1b1-0caf-4d68-98c4-6bdd441c23fb
caps.latest.revision: 0
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
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 07b8db673b2db27f456f0e7228695c83497d1278
ms.contentlocale: zh-tw
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4458"></a>編譯器警告 （層級 4） C4458
  
> 宣告的 '*識別碼*' 會隱藏類別成員
  
宣告*識別碼*在區域範圍會隱藏相同名稱的宣告*識別碼*在類別範圍。 這項警告可讓您知道要參考*識別碼*在這個範圍中解析本機宣告的版本，而不是類別成員版本，這可能或可能不到您的意圖。 若要修正此問題，我們建議您提供沒有衝突與類別成員名稱的本機變數名稱。  
    
## <a name="example"></a>範例
  
下列範例會產生 C4458，因為參數`x`和區域變數`y`中`member_fn`類別中有相同的資料成員名稱。 若要修正此問題，請使用不同的參數和區域變數的名稱。  
  
```cpp  
// C4458_hide.cpp
// compile with: cl /W4 /c C4458_hide.cpp

struct S {
    int x;
    float y;
    void member_fn(long x) {   // C4458
        double y;  // C4458
        y = x;  
        // To fix this issue, change the parameter name x
        // and local name y to something that does not 
        // conflict with the data member names.
    }
} s;
```  
