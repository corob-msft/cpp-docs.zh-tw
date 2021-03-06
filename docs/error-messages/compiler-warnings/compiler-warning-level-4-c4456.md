---
title: 編譯器警告 （層級 4） C4456
ms.date: 11/04/2016
f1_keywords:
- C4456
helpviewer_keywords:
- C4456
ms.assetid: 5ab39fc1-0e19-461b-842b-4da80560b044
ms.openlocfilehash: 006628721598d838070412c895f64b9a8d3de4e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452581"
---
# <a name="compiler-warning-level-4-c4456"></a>編譯器警告 （層級 4） C4456

> 宣告的 '*識別碼*' 會隱藏先前的區域宣告

Deklarace*識別碼*本機範圍內隱藏相同名稱的前一個區域宣告的宣告。 這項警告可讓您知道的參考*識別碼*在區域範圍中解析的區域宣告的版本，不先前 local，這可能會或可能不到您的意圖。 若要修正此問題，我們建議您提供與其他的本機名稱的區域變數名稱，不會衝突。

## <a name="example"></a>範例

下列範例會產生 C4456，因為迴圈控制變數`int x`和 區域變數`double x`在`member_fn`有相同的名稱。 若要修正此問題，使用不同的本機變數的名稱。

```cpp
// C4456_hide.cpp
// compile with: cl /W4 /c C4456_hide.cpp

struct S {
    void member_fn(unsigned u) {
        double x = 0;
        for (int x = 0; x < 10; ++x) {  // C4456
            u += x; // uses local int x
        }
        x += u; // uses local double x
    }
} s;
```
