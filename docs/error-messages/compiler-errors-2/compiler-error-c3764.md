---
title: 編譯器錯誤 C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 498aefae4dfe8fd13184b9da1685494d533575dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556425"
---
# <a name="compiler-error-c3764"></a>編譯器錯誤 C3764

'override_function': 無法覆寫基底類別方法 'base_class_function'

編譯器偵測到格式不正確的覆寫。 例如，基底類別函式未`virtual`。 如需詳細資訊，請參閱 <<c0> [ 覆寫](../../windows/override-cpp-component-extensions.md)。

## <a name="example"></a>範例

下列範例會產生 C3764。

```
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>範例

C3764 也可能發生於基底類別方法是明確，和名為覆寫。 下列範例會產生 C3764。

```
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```