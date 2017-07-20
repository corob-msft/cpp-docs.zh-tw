---
title: "編譯器錯誤 C3292 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3292
dev_langs:
- C++
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: 5
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
ms.openlocfilehash: 6b5b5189115e9c6803c1d2b8687819fcbedac593
ms.contentlocale: zh-tw
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3292"></a>編譯器錯誤 C3292
無法重新開啟 cli 命名空間  
  
 無法在程式碼中宣告 cli 命名空間。  如需詳細資訊，請參閱[平台、 default 和 cli 命名空間](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)。  
  
## <a name="example"></a>範例  
 下列範例會產生 C3292：  
  
```  
// C3292.cpp  
// compile with: /clr /c  
namespace cli {};   // C3292  
```