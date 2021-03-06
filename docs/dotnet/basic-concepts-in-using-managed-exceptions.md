---
title: 使用 Managed 例外狀況中的基本概念
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: 45244ace414fc073956684088ac43eb9b92f1e5b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588236"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>使用 Managed 例外狀況中的基本概念

本主題討論在 managed 應用程式處理的例外狀況。 也就是使用編譯的應用程式 **/clr**編譯器選項。

## <a name="in-this-topic"></a>本主題內容

- [擲回例外狀況下 /clr](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [Try/Catch 區塊 CLR 延伸模組](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>備註

如果您使用編譯 **/clr**選項，您可以處理 CLR 例外狀況，以及標準[c + + 例外狀況處理](../cpp/cpp-exception-handling.md)並[結構化例外狀況處理](../cpp/structured-exception-handling-c-cpp.md)(SEH)。 CLR 例外狀況是由 managed 型別擲回任何例外狀況。 [System:: exception](https://msdn.microsoft.com/library/system.exception.aspx)類別提供許多有用的方法，來處理 CLR 例外狀況，並建議為使用者定義的例外狀況類別的基底類別。

攔截例外狀況衍生自介面的型別不受 **/clr**。 此外，通用語言執行平台不允許您攔截堆疊溢位例外狀況;堆疊溢位例外狀況將會終止處理序。

如需有關在 managed 和 unmanaged 應用程式中的例外狀況處理差異的詳細資訊，請參閱 <<c0> [ 例外狀況處理行為下 Managed Extensions for c + + 中的差異](../dotnet/differences-in-exception-handling-behavior-under-clr.md)。

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> 擲回例外狀況下 /clr

C + + throw 運算式會擴充到擲回 CLR 型別控制代碼。 下列範例會建立自訂例外狀況類型，然後擲回該類型的執行個體：

```
// clr_exception_handling.cpp
// compile with: /clr /c
ref struct MyStruct: public System::Exception {
public:
   int i;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   throw pMyStruct;
}
```

實值型別必須進行 boxed 處理之前擲回：

```
// clr_exception_handling_2.cpp
// compile with: /clr /c
value struct MyValueStruct {
   int i;
};

void GlobalFunction() {
   MyValueStruct v = {11};
   throw (MyValueStruct ^)v;
}
```

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Try/Catch 區塊 CLR 延伸模組

相同**嘗試**/**攔截**區塊結構可用來擷取 CLR 和原生例外狀況：

```
// clr_exception_handling_3.cpp
// compile with: /clr
using namespace System;
ref struct MyStruct : public Exception {
public:
   int i;
};

struct CMyClass {
public:
   double d;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   pMyStruct->i = 11;
   throw pMyStruct;
}

void GlobalFunction2() {
   CMyClass c = {2.0};
   throw c;
}

int main() {
   for ( int i = 1; i >= 0; --i ) {
      try {
         if ( i == 1 )
            GlobalFunction2();
         if ( i == 0 )
            GlobalFunction();
      }
      catch ( CMyClass& catchC ) {
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );
         Console::WriteLine( catchC.d );
      }
      catch ( MyStruct^ catchException ) {
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );
         Console::WriteLine( catchException->i );
      }
   }
}
```

### <a name="output"></a>輸出

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>C + + 物件復原順序

回溯會具有解構函式可能擲回的函式和處理函式之間，執行階段堆疊上的任何 c + + 物件時發生。 因為 CLR 型別在堆積上配置，所以回溯不適用於它們。

擲回的例外狀況的事件順序如下所示：

1. 執行階段會逐步引導堆疊以尋找適當的 catch 子句，或在 SEH，除了 SEH，來攔截例外狀況篩選條件。 Catch 子句會先搜尋語彙順序，然後動態地向下呼叫堆疊。

1. 一旦找到正確的處理常式，回溯堆疊時該點。 在堆疊上每個函式呼叫，其本機物件會解構和 __finally 區塊執行，大部分從向外的巢狀。

1. 一旦回溯堆疊時，會執行 catch 子句。

### <a name="catching-unmanaged-types"></a>攔截 Unmanaged 的類型

擲回的未受管理的物件型別時，它會包裝類型的例外狀況[System::Runtime.InteropServices::SEHException](https://msdn.microsoft.com/library/system.runtime.interopservices.sehexception.aspx)。 當搜尋適當**攔截**子句中，有兩種可能性。

- 如果遇到原生的 c + + 型別時，會解除包裝例外狀況，並將其相較於遇到的型別。 這項比較可讓您以一般方式攔截原生 c + + 型別。

- 不過，如果**攔截**型別的子句**SEHException**或任何其基底類別會在第一次檢查時，子句會攔截的例外狀況。 因此，您應該將任何攔截的 CLR 型別子句之前，先攔截原生 c + + 類型的所有 catch 子句。

請注意：

```
catch(Object^)
```

和

```
catch(...)
```

兩者會攔截任何擲回的型別，包括 SEH 例外狀況。

如果 catch(Object^) 所攔截到未受管理的類型時，它不會終結擲回的物件。

當擲回或攔截的 unmanaged 例外狀況時，我們建議您使用[/EHsc](../build/reference/eh-exception-handling-model.md)編譯器選項，而非 **/EHs**或是 **/EHa**。

## <a name="see-also"></a>另請參閱

[例外狀況處理](../windows/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)<br/>
[例外狀況處理](../cpp/exception-handling-in-visual-cpp.md)