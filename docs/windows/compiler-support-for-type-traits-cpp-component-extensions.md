---
title: "類型特性的編譯器支援 (C++ 元件擴充功能) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__is_simple_value_class"
  - "__has_trivial_destructor"
  - "__has_assign"
  - "__is_union"
  - "__is_class"
  - "__is_abstract"
  - "__has_trivial_assign"
  - "__has_virtual_destructor"
  - "__is_ref_array"
  - "__is_base_of"
  - "__has_copy"
  - "__is_polymorphic"
  - "__has_nothrow_constructor"
  - "__is_ref_class"
  - "__is_delegate"
  - "__is_convertible_to"
  - "__is_value_class"
  - "__is_interface_class"
  - "__has_nothrow_copy"
  - "__is_sealed"
  - "__has_trivial_constructor"
  - "__has_trivial_copy"
  - "__is_enum"
  - "__has_nothrow_assign"
  - "__has_finalizer"
  - "__is_empty"
  - "__is_pod"
  - "__has_user_destructor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__is_class 關鍵字 [C++]"
  - "__is_pod 關鍵字 [C++]"
  - "__is_delegate 關鍵字 [C++]"
  - "__is_value_class 關鍵字 [C++]"
  - "__has_copy 關鍵字 [C++]"
  - "__has_nothrow_copy 關鍵字 [C++]"
  - "__is_interface_class 關鍵字 [C++]"
  - "__is_sealed 關鍵字 [C++]"
  - "__is_convertible_to 關鍵字 [C++]"
  - "__is_ref_class 關鍵字 [C++]"
  - "__has_trivial_copy 關鍵字 [C++]"
  - "__has_user_destructor 關鍵字 [C++]"
  - "__is_abstract 關鍵字 [C++]"
  - "__is_empty 關鍵字 [C++]"
  - "__has_trivial_assign 關鍵字 [C++]"
  - "__has_nothrow_constructor 關鍵字 [C++]"
  - "__is_ref_array 關鍵字 [C++]"
  - "__is_base_of 關鍵字 [C++]"
  - "__has_nothrow_assign 關鍵字 [C++]"
  - "__has_virtual_destructor 關鍵字 [C++]"
  - "__has_finalizer 關鍵字 [C++]"
  - "__is_union 關鍵字 [C++]"
  - "__has_assign 關鍵字 [C++]"
  - "__has_trivial_destructor 關鍵字 [C++]"
  - "__is_polymorphic 關鍵字 [C++]"
  - "__is_enum 關鍵字 [C++]"
  - "__is_simple_value_class 關鍵字 [C++]"
  - "__has_trivial_constructor 關鍵字 [C++]"
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 類型特性的編譯器支援 (C++ 元件擴充功能)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

編譯器支援 *輸入特性*, ，表示在編譯時期型別的各種特性。  
  
## <a name="all-runtimes"></a>所有執行階段  
 **註解**  
  
 類型特性特別適用於撰寫程式庫的程式設計人員。  
  
 下列清單包含編譯器所支援的類型特性。 如果不符合類型特性名稱所指定的條件，則所有類型特性都會傳回 `false`。  
  
 (下面程式碼範例只在撰寫 [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)]。 但除非另有說明，否則在 [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] 中也會支援對應的類型特性。 「平台類型」一詞是指 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 類型或 Common Language Runtime 類型。)  
  
-   `__has_assign(` `type` `)`  
  
     如果平台或原生類型具有複製指派運算子，則傳回 true。  
  
    ```  
  
    ref struct R {  
    void operator=(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_assign(R));  
    }  
  
    ```  
  
-   `__has_copy(` `type` `)`  
  
     如果平台或原生類型具有複製建構函式，則傳回 true。  
  
    ```  
  
    ref struct R {  
    R(R% r) {}  
    };  
  
    int main() {  
    System::Console::WriteLine(__has_copy(R));  
    }  
  
    ```  
  
-   `__has_finalizer(` `type` `)`  
  
     (在 [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] 中不支援。)如果 CLR 類型具有完成項，則傳回 true。 請參閱 [解構函式和完成項中 Visual c + +](../misc/destructors-and-finalizers-in-visual-cpp.md) 如需詳細資訊。  
  
    ```  
  
    using namespace System;  
    ref struct R {  
    ~R() {}  
    protected:  
    !R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_finalizer(R));  
    }  
  
    ```  
  
-   `__has_nothrow_assign(` `type` `)`  
  
     如果複製指派運算子具有空的例外狀況規格，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    void operator=(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_constructor(` `type` `)`  
  
     如果預設建構函式具有空的例外狀況規格，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S() throw() {}  
    };  
  
    int main() {  
    __has_nothrow_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_nothrow_copy(` `type` `)`  
  
     如果複製建構函式具有空的例外狀況規格，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    S(S& r) throw() {}  
    };  
  
    int main() {  
    __has_nothrow_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_assign(` `type` `)`  
  
     如果類型具有編譯器產生的一般指派運算子，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_assign(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_constructor(` `type` `)`  
  
     如果類型具有編譯器產生的一般建構函式，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_constructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_copy(` `type` `)`  
  
     如果類型具有編譯器產生的複製建構函式，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_copy(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_trivial_destructor(` `type` `)`  
  
     如果類型具有編譯器產生的一般解構函式，則傳回 true。  
  
    ```  
  
    // has_trivial_destructor.cpp  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __has_trivial_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__has_user_destructor(` `type` `)`  
  
     如果平台或原生類型具有使用者宣告的解構函式，則傳回 true。  
  
    ```  
  
    // has_user_destructor.cpp  
  
    using namespace System;  
    ref class R {  
    ~R() {}  
    };  
  
    int main() {  
    Console::WriteLine(__has_user_destructor(R));  
    }  
  
    ```  
  
-   `__has_virtual_destructor(` `type` `)`  
  
     如果類型具有虛擬解構函式，則傳回 true。  
  
     `__has_virtual_destructor` 也適用於平台類型，且任何平台類型中的使用者定義解構函式都是虛擬解構函式。  
  
    ```  
  
    // has_virtual_destructor.cpp  
    #include <stdio.h>  
    struct S {  
    virtual ~S() {}  
    };  
  
    int main() {  
    __has_virtual_destructor(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_abstract(` `type` `)`  
  
     如果類型是抽象類型，則傳回 true。 如需有關原生的抽象類型的詳細資訊，請參閱 [抽象](../windows/abstract-cpp-component-extensions.md)。  
  
     `__is_abstract` 也適用於平台類型。 至少有一個成員的介面是參考類型，至少有一個抽象成員的介面是參考類型。 如需有關抽象的平台類型的詳細資訊，請參閱 [抽象類別](../cpp/abstract-classes-cpp.md)  
  
    ```  
  
    // is_abstract.cpp  
    #include <stdio.h>  
    struct S {  
    virtual void Test() = 0;  
    };  
  
    int main() {  
    __is_abstract(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_base_of(` `base` `,` `derived` `)`  
  
     如果第一種類型是第二種類型的基底類別，或這兩種類型相同，則傳回 true。  
  
     `__is_base_of` 也適用於平台類型。 比方說，它會傳回 true，如果第一種 [介面類別](../windows/interface-class-cpp-component-extensions.md) 和第二個型別實作的介面。  
  
    ```  
  
    // is_base_of.cpp  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    __is_base_of(S, T) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_base_of(S, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_class(` `type` `)`  
  
     如果類型是原生類別或結構，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_class(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_convertible_to(` `from` `,`  `to` `)`  
  
     如果第一個類型可轉換成第二個類型，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
    struct T : public S {};  
  
    int main() {  
    S * s = new S;  
    T * t = new T;  
    s = t;  
    __is_convertible_to(T, S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_delegate(` `type` `)`  
  
     如果 `type` 是委派，則傳回 true。 如需詳細資訊，請參閱 [委派 （c + + 元件擴充功能）](../windows/delegate-cpp-component-extensions.md)。  
  
    ```  
  
    delegate void MyDel();  
    int main() {  
    System::Console::WriteLine(__is_delegate(MyDel));  
    }  
  
    ```  
  
-   `__is_empty(` `type` `)`  
  
     如果類型沒有執行個體資料成員，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    int Test() {}  
    static int i;  
    };  
    int main() {  
    __is_empty(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_enum(` `type` `)`  
  
     如果類型是原生列舉，則傳回 true。  
  
    ```  
  
    // is_enum.cpp  
    #include <stdio.h>  
    enum E { a, b };  
  
    struct S {  
    enum E2 { c, d };  
    };  
  
    int main() {  
    __is_enum(E) == true ?  
    printf("true\n") : printf("false\n");  
  
    __is_enum(S::E2) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_interface_class(` `type` `)`  
  
     如果傳遞平台介面，則傳回 true。 如需詳細資訊，請參閱 [介面類別](../windows/interface-class-cpp-component-extensions.md)。  
  
    ```  
  
    // is_interface_class.cpp  
  
    using namespace System;  
    interface class I {};  
    int main() {  
    Console::WriteLine(__is_interface_class(I));  
    }  
  
    ```  
  
-   `__is_pod(` `type` `)`  
  
     如果類型是類別或等位，且不具建構函式、私人或受保護的非靜態成員、不具基底類別和虛擬函式，則傳回 true。 如需 POD 的詳細資訊，請參閱 C++ 標準的 8.5.1/1、9/4 和 3.9/10 小節。  
  
     `__is_pod` 對於基本類型會傳回 false。  
  
    ```  
  
    #include <stdio.h>  
    struct S {};  
  
    int main() {  
    __is_pod(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_polymorphic(` `type` `)`  
  
     如果原生類型具有虛擬函式，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    struct S {  
    virtual void Test(){}  
    };  
  
    int main() {  
    __is_polymorphic(S) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_ref_array(` `type` `)`  
  
     如果傳遞平台陣列，則傳回 true。 如需詳細資訊，請參閱 [陣列](../windows/arrays-cpp-component-extensions.md)。  
  
    ```  
  
    using namespace System;  
    int main() {  
    array<int>^ x = gcnew array<int>(10);  
    Console::WriteLine(__is_ref_array(array<int>));  
    }  
  
    ```  
  
-   `__is_ref_class(` `type` `)`  
  
     如果傳遞參考類別，則傳回 true。 如需有關使用者定義的參考類型的詳細資訊，請參閱 [類別和結構](../windows/classes-and-structs-cpp-component-extensions.md)。  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    int main() {  
    Console::WriteLine(__is_ref_class(Buffer));  
    Console::WriteLine(__is_ref_class(R));  
    }  
  
    ```  
  
-   `__is_sealed(` `type` `)`  
  
     如果傳遞平台或標示為密封的原生類型，則傳回 true。 如需詳細資訊，請參閱 [密封](../windows/sealed-cpp-component-extensions.md)。  
  
    ```  
  
    ref class R sealed{};  
    int main() {  
    System::Console::WriteLine(__is_sealed(R));  
    }  
  
    ```  
  
-   `__is_simple_value_class(` `type` `)`  
  
     如果傳遞值類型，且其中不含對記憶體回收堆積的參考，則傳回 true。 如需有關使用者定義的實值類型的詳細資訊，請參閱 [類別和結構](../windows/classes-and-structs-cpp-component-extensions.md)。  
  
    ```  
  
    using namespace System;  
    ref class R {};  
    value struct V {};  
    value struct V2 {  
    R ^ r;   // not a simnple value type  
    };  
  
    int main() {  
    Console::WriteLine(__is_simple_value_class(V));  
    Console::WriteLine(__is_simple_value_class(V2));  
    }  
  
    ```  
  
-   `__is_union(` `type` `)`  
  
     如果類型是等位，則傳回 true。  
  
    ```  
  
    #include <stdio.h>  
    union A {  
    int i;  
    float f;  
    };  
  
    int main() {  
    __is_union(A) == true ?  
    printf("true\n") : printf("false\n");  
    }  
  
    ```  
  
-   `__is_value_class(` `type` `)`  
  
     如果傳遞值類型，則傳回 true。 如需有關使用者定義的實值類型的詳細資訊，請參閱 [類別和結構](../windows/classes-and-structs-cpp-component-extensions.md)。  
  
    ```  
  
    value struct V {};  
  
    int main() {  
    System::Console::WriteLine(__is_value_class(V));  
    }  
  
    ```  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **註解**  
  
  `__has_finalizer(`*類型*`)` 不支援類型特性，因為此平台不支援完成項。  
  
### <a name="requirements"></a>需求  
 編譯器選項： **/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **註解**  
  
 (沒有這項功能的平台特定備註。)  
  
### <a name="requirements"></a>需求  
 編譯器選項： **/clr**  
  
### <a name="examples"></a>範例  
 **範例**  
  
 下列程式碼範例示範如何使用類別樣板中公開的編譯器型別特性 **/clr** 編譯。 如需詳細資訊，請參閱 [Windows 執行階段和 Managed 樣板](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)。  
  
```  
// compiler_type_traits.cpp  
// compile with: /clr  
using namespace System;  
  
template <class T>  
ref struct is_class {  
   literal bool value = __is_ref_class(T);  
};  
  
ref class R {};  
  
int main () {  
   if (is_class<R>::value)  
      Console::WriteLine("R is a ref class");  
   else  
      Console::WriteLine("R is not a ref class");  
}  
```  
  
 **輸出**  
  
```Output  
R is a ref class  
```  
  
## <a name="see-also"></a>另請參閱  
 [執行階段平台的元件擴充功能](../windows/component-extensions-for-runtime-platforms.md)