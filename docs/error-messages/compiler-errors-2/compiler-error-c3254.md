---
title: 編譯器錯誤 C3254
ms.date: 11/04/2016
f1_keywords:
- C3254
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
ms.openlocfilehash: 7e051c6c44d3b85f6f3faaf5380ecf54cba5d73c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50470664"
---
# <a name="compiler-error-c3254"></a>編譯器錯誤 C3254

'明確覆寫': 類別包含明確覆寫 'override'，但不是衍生自包含函式宣告的介面

當您[明確覆寫](../../cpp/explicit-overrides-cpp.md)方法，包含覆寫的類別必須，直接或間接衍生，包含函式的型別從您正在覆寫。

下列範例會產生 C3254:

```
// C3254.cpp
__interface I
{
   void f();
};

__interface I1 : I
{
};

struct A /* : I1 */
{
   void I1::f()
   {   // C3254, uncomment : I1 to resolve this C3254
   }
};

int main()
{
}
```