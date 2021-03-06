---
title: 明確覆寫 (C + + /cli 和 C + + /CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- overriding, override [C++]
ms.assetid: 4ec3eaf5-163b-4df8-8f16-7a2ec04c3d0f
ms.openlocfilehash: 54f3d50b3a47890e6f3dd68c41832fa3d1e13e59
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459818"
---
# <a name="explicit-overrides--ccli-and-ccx"></a>明確覆寫 (C + + /cli 和 C + + /CX)

本主題討論如何明確覆寫基底類別或介面的成員。 具名的 （明確） 覆寫應該只用來覆寫方法，以使用衍生的方法具有不同的名稱。

## <a name="all-runtimes"></a>所有執行階段

### <a name="syntax"></a>語法

```cpp
overriding-function-declarator = type::function [,type::function] { overriding-function-definition }
overriding-function-declarator = function { overriding-function-definition }
```

### <a name="parameters"></a>參數

*覆寫函式宣告子*<br/>
覆寫的函式的傳回型別、 名稱和引數清單。  請注意，覆寫的函式沒有覆寫的函式相同的名稱。

*type*<br/>
包含函式來覆寫基底型別。

*function*<br/>
若要覆寫的一或多個函式名稱的逗號分隔清單。

*覆寫函式定義*<br/>
定義覆寫的函式的函式主體陳述式。

### <a name="remarks"></a>備註

使用明確覆寫建立方法簽章的別名，或提供的方法使用相同的簽章的不同實作。

如需修改繼承型別和繼承型別成員的行為的詳細資訊，請參閱 <<c0> [ 覆寫規範](../windows/override-specifiers-cpp-component-extensions.md)。

## <a name="windows-runtime"></a>Windows 執行階段

### <a name="requirements"></a>需求

編譯器選項：`/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="remarks"></a>備註

明確的相關資訊會覆寫原生程式碼或程式碼編譯`/clr:oldSyntax`，請參閱 <<c2> [ 明確覆寫](../cpp/explicit-overrides-cpp.md)。

### <a name="requirements"></a>需求

編譯器選項：`/clr`

### <a name="examples"></a>範例

下列程式碼範例顯示簡單、 隱含覆寫和成員的實作在基底介面中，不使用明確覆寫。

```cpp
// explicit_override_1.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void f() {
      System::Console::WriteLine("X::f override of I1::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   MyI -> f();
}
```

```Output
X::f override of I1::f
```

下列程式碼範例示範如何實作所有介面成員使用一般的簽章中，使用明確覆寫語法。

```cpp
// explicit_override_2.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

interface struct I2 {
   virtual void f();
};

ref struct X : public I1, I2 {
   virtual void f() = I1::f, I2::f {
      System::Console::WriteLine("X::f override of I1::f and I2::f");
   }
};

int main() {
   I1 ^ MyI = gcnew X;
   I2 ^ MyI2 = gcnew X;
   MyI -> f();
   MyI2 -> f();
}
```

```Output
X::f override of I1::f and I2::f
X::f override of I1::f and I2::f
```

下列程式碼範例顯示如何函式覆寫可以有不同的名稱，從它所實作的函式。

```cpp
// explicit_override_3.cpp
// compile with: /clr
interface struct I1 {
   virtual void f();
};

ref class X : public I1 {
public:
   virtual void g() = I1::f {
      System::Console::WriteLine("X::g");
   }
};

int main() {
   I1 ^ a = gcnew X;
   a->f();
}
```

```Output
X::g
```

下列程式碼範例顯示實作型別安全集合的明確介面實作。

```cpp
// explicit_override_4.cpp
// compile with: /clr /LD
using namespace System;
ref class R : ICloneable {
   int X;

   virtual Object^ C() sealed = ICloneable::Clone {
      return this->Clone();
   }

public:
   R() : X(0) {}
   R(int x) : X(x) {}

   virtual R^ Clone() {
      R^ r = gcnew R;
      r->X = this->X;
      return r;
   }
};
```

## <a name="see-also"></a>另請參閱

[適用於.NET 和 UWP 的元件延伸模組](../windows/component-extensions-for-runtime-platforms.md)