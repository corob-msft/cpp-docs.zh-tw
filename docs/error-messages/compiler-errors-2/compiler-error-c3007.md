---
title: "編譯器錯誤 C3007 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3007
dev_langs:
- C++
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
caps.latest.revision: 6
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
ms.openlocfilehash: 9bc22dfa00491c7ff4f1871fe494bd7719b1b802
ms.contentlocale: zh-tw
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3007"></a>編譯器錯誤 C3007
'arg' : OpenMP 'directive' 指示詞上的子句不接受引數  
  
 OpenMP 指示詞具有引數，但指示詞不接受引數。  
  
 下列範例會產生 C3007：  
  
```  
// C3007.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel for ordered(2)   // C3007  
}  
```