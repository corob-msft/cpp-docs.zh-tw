---
title: 編譯器錯誤 C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: ec6725472d31b0b2ade0cd73da4440036239fde3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598555"
---
# <a name="compiler-error-c3849"></a>編譯器錯誤 C3849

運算式的類型 'type' 的函式樣式呼叫會失去所有數字可用運算子多載的 const 及/或 volatile 限定詞

具有指定的常數 volatile 類型的變數只能呼叫成員函式定義包含大於或等於常數 volatile 限定性條件。

若要修正這個錯誤，提供適當的成員函式。 當轉換導致遺失的限定性條件時，您無法執行轉換上的 const 或 volatile 限定的物件。 您可以取得限定詞，但您不能遺失轉換中的限定詞。

下列範例會產生 C3849:

```
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```