---
title: 編譯器錯誤 C3280
ms.date: 11/04/2016
f1_keywords:
- C3280
helpviewer_keywords:
- C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
ms.openlocfilehash: b43ea73a626ba35f58054a94046915d4eba97181
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566240"
---
# <a name="compiler-error-c3280"></a>編譯器錯誤 C3280

'class' : 無法將 Managed 類型的成員函式編譯成 Unmanaged 函式

無法將 Managed 類別成員函式編譯成 Unmanaged 函式。

下列範例會產生 C3280：

```
// C3280_2.cpp
// compile with: /clr
ref struct A {
   void func();
};

#pragma managed(push,off)

void A::func()   // C3280
{
}

#pragma managed(pop)
```
