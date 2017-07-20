---
title: "auto_ptr 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- auto_ptr
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
dev_langs:
- C++
helpviewer_keywords:
- auto_ptr class
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 320dbc4d09bfcc65fce8471ce23e127f28deb6b9
ms.contentlocale: zh-tw
ms.lasthandoff: 04/29/2017

---
# <a name="autoptr-class"></a>auto_ptr 類別
以智慧型指標包裝資源，確保當控制離開區塊時，會自動終結該資源。  
  
 更適用的 `unique_ptr` 類別會取代 `auto_ptr`。 如需詳細資訊，請參閱 [unique_ptr 類別](../standard-library/unique-ptr-class.md)。  
  
 如需 `throw()` 和例外狀況處理的詳細資訊，請參閱[例外狀況規格 (throw)](../cpp/exception-specifications-throw-cpp.md)。  
  
## <a name="syntax"></a>語法  
 ```   
class auto_ptr {
public:
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```  
#### <a name="parameters"></a>參數  
 `right`  
 要從中取得現有資源的 `auto_ptr`。  
  
 `ptr`  
 此指標指定了要取代的已儲存指標。  
  
## <a name="remarks"></a>備註  
 此範本類別描述智慧型指標，呼叫`auto_ptr`，配置物件。 這個指標必須是 null，或指定 `new` 所配置的物件。 如果將 `auto_ptr` 的儲存值指派給另一個物件，則會轉移擁有權。 (轉移後，會以 null 指標取代儲存值。)`auto_ptr<Type>` 的解構函式會刪除配置物件。 `auto_ptr<Type>` 可確保當控制離開區塊時 (即使是透過擲回例外狀況)，會自動刪除配置物件。 您不應該建構兩個擁有相同物件的 `auto_ptr<Type>` 物件。  
  
 您可以將 `auto_ptr<Type>` 物件當做函式呼叫的引數，以傳值方式來傳遞。 `auto_ptr` 不能是任何標準程式庫容器的項目。 您無法透過 C++ 標準程式庫容器可靠地管理一系列的 `auto_ptr<Type>` 物件。  
  
## <a name="members"></a>Members  
  
### <a name="constructors"></a>建構函式  
  
|||  
|-|-|  
|[auto_ptr](#auto_ptr)|`auto_ptr` 類型物件的建構函式。|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[element_type](#element_type)|此類型是樣板參數 `Type` 的同義字。|  
  
### <a name="member-functions"></a>成員函式  
  
|||  
|-|-|  
|[get](#get)|這個成員函式會傳回儲存的指標 `myptr`。|  
|[release](#release)|這個成員會以 null 指標取代儲存的指標 `myptr`，並傳回先前儲存的指標。|  
|[reset](#reset)|這個成員函式只有在儲存的指標值 `myptr` 因函式呼叫而變更時，才會評估運算式 `delete myptr`。 然後會以 `ptr` 取代儲存的指標。|  
  
### <a name="operators"></a>運算子  
  
|||  
|-|-|  
|[operator=](#op_eq)|指派運算子，將擁有權從一個 `auto_ptr` 物件轉移至另一個物件。|  
|[operator*](#op_star)|`auto_ptr` 類型物件的取值運算子。|  
|[operator->](#operator-_gt)|允許成員存取的運算子。|  
|[operator auto_ptr\<Other>](#op_auto_ptr_lt_other_gt)|從一種 `auto_ptr` 轉換成另一種 `auto_ptr`。|  
|[operator auto_ptr_ref\<Other>](#op_auto_ptr_ref_lt_other_gt)|從 `auto_ptr` 轉換成 `auto_ptr_ref`。|  
  
## <a name="requirements"></a>需求  
 **標頭：**\<memory>  
  
 **命名空間：** std  
  
##  <a name="auto_ptr"></a> auto_ptr::auto_ptr  
 `auto_ptr` 類型物件的建構函式。  
  
```   
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>  
auto _ptr(auto _ptr<Other>& right) throw();
```  
  
### <a name="parameters"></a>參數  
 `ptr`  
 `auto_ptr` 所封裝物件的指標。  
  
 `right`  
 要由建構函式所複製的 `auto_ptr` 物件。  
  
### <a name="remarks"></a>備註  
 第一個建構函式會將 `ptr` 儲存在 **myptr**，後者就是所配置物件的預存指標。 第二個建構函式會儲存 `right`，以轉移 `right` 中所儲存指標的擁有權。 **myptr**中的 [release](#release)。  
  
 第三個建構函式的行為與第二個建構函式相同，差異在於它會儲存 **right**. `ref`. **release** 於 **myptr**，其中 `ref` 是 `right` 中所儲存的參考。  
  
 範本建構函式的行為與第二個建構函式相同，但前提是 **Other** 的指標可以隱含地轉換為 **Type** 的指標。  
  
### <a name="example"></a>範例  
  
```cpp  
// auto_ptr_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      cout << "Constructing " << ( void* )this  << endl;   
      x = i;  
      bIsConstructed = true;  
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << endl;   
      bIsConstructed = false;  
   };  
   Int &operator++( )   
   {  
      x++;  
      return *this;  
   };  
   int x;  
private:  
   bool bIsConstructed;  
};  
  
void function ( auto_ptr<Int> &pi )  
{  
   ++( *pi );  
   auto_ptr<Int> pi2( pi );  
   ++( *pi2 );  
   pi = pi2;  
}  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   cout << pi->x << endl;  
   function( pi );  
   cout << pi->x << endl;  
}  
```  
  
```Output  
Constructing 00311AF8  
5  
7  
Destructing 00311AF8  
```  
  
##  <a name="element_type"></a> auto_ptr::element_type  
 此類型是範本參數 **Type** 的同義字。  
  
```  
 
typedef Type element  _type;  
```  
  
##  <a name="get"></a> auto_ptr::get  
 這個成員函式會傳回儲存的指標 **myptr**。  
  
```   
Type *get() const throw();
```  
  
### <a name="return-value"></a>傳回值  
 儲存的指標 **myptr**。  
  
### <a name="example"></a>範例  
  
```cpp  
// auto_ptr_get.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int   
{  
public:  
   Int(int i)   
   {  
      x = i;  
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;   
   };  
   ~Int( )   
   {  
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;   
   };  
  
   int x;  
  
};  
  
int main( )   
{  
   auto_ptr<Int> pi ( new Int( 5 ) );  
   pi.reset( new Int( 6 ) );  
   Int* pi2 = pi.get ( );  
   Int* pi3 = pi.release ( );  
   if (pi2 == pi3)  
      cout << "pi2 == pi3" << endl;  
   delete pi3;  
}  
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="op_eq"></a> auto_ptr::operator=  
 指派運算子，將擁有權從一個 `auto_ptr` 物件轉移至另一個物件。  
  
```  
template <class Other>  
auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```  
  
### <a name="parameters"></a>參數  
 `right`  
 `auto_ptr` 類型的物件。  
  
### <a name="return-value"></a>傳回值  
 `auto_ptr`\< **Type**> 類型之物件的參考。  
  
### <a name="remarks"></a>備註  
 只有在儲存的指標 **myptr** 因指派而變更時，這項指派才會評估運算式 **delete myptr**。 它接著會儲存 \_*Right*，以轉移 _*Right* 中所儲存指標的擁有權。 **myptr**中的 [release](#release)。 此函式會傳回 **\*this**。  
  
### <a name="example"></a>範例  
  如需成員運算子的使用範例，請參閱 [auto_ptr::auto_ptr](#auto_ptr)。  
  
##  <a name="op_star"></a> auto_ptr::operator*  
 `auto_ptr` 類型物件的取值運算子。  
  
```   
Type& operator*() const throw();
```  
  
### <a name="return-value"></a>傳回值  
 指標所擁有 **Type** 類型之物件的參考。  
  
### <a name="remarks"></a>備註  
 間接取值運算子會傳回 `*`[get](#get)。 因此，儲存的指標不得為 Null。  
  
### <a name="example"></a>範例  
  如需成員函式用法的範例，請參閱 [auto_ptr::auto_ptr](#auto_ptr)。  
  
##  <a name="auto_ptr__operator-_gt"></a> auto_ptr::operator-&gt;  
 允許成員存取的運算子。  
  
```   
Type * operator->() const throw();
```  
  
### <a name="return-value"></a>傳回值  
 **auto_ptr** 所擁有物件的成員。  
  
### <a name="remarks"></a>備註  
 選取運算子會傳回 [get](#get)`( )`，如此一來，運算式 *ap*-> **member** 的運作方式會與下列運算式相同：(*ap*. **get**( ) )-> **member**，其中 *ap* 是類別 `auto_ptr`\< **Type**> 的物件。 因此，儲存的指標不得為 Null，而且 **Type** 必須是包含 **member** 成員的類別、結構或等位類型。  
  
### <a name="example"></a>範例  
  如需成員函式用法的範例，請參閱 [auto_ptr::auto_ptr](#auto_ptr)。  
  
##  <a name="op_auto_ptr_lt_other_gt"></a> auto_ptr::operator auto_ptr&lt;Other&gt;  
 從一種 `auto_ptr` 轉換成另一種 `auto_ptr`。  
  
```   
template <class Other>  
operator auto _ptr<Other>() throw();
```  
  
### <a name="return-value"></a>傳回值  
 類型轉型運算子會傳回 `auto_ptr` \< **Other**>( **\*this**)。  
  
### <a name="example"></a>範例  
  
```cpp  
// auto_ptr_op_auto_ptr.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
int main()  
{  
   auto_ptr<int> pi ( new int( 5 ) );  
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;  
}  
```  
  
##  <a name="op_auto_ptr_ref_lt_other_gt"></a> auto_ptr::operator auto_ptr_ref&lt;Other&gt;  
 從 `auto_ptr` 轉型成 **auto_ptr_ref**。  
  
```   
template <class Other>  
operator auto _ptr  _ref<Other>() throw();
```  
  
### <a name="return-value"></a>傳回值  
 類型轉型運算子會傳回 **auto_ptr_ref**\< **Other**>( **\*this**)。  
  
### <a name="example"></a>範例  
  
```cpp  
// auto_ptr_op_auto_ptr_ref.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;  
  
class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer  
    // f(ciap);   
    f(iap); // compiles, but gives up ownership of pointer  

            // here, iap owns a destroyed pointer so the following is bad:  
            // *iap = 5; // BOOM  

    cout << "main exiting\n";
}
```  
  
```Output  
~C:  2  
main exiting  
~C:  1  
```  
  
##  <a name="release"></a> auto_ptr::release  
 這個成員會以 Null 指標取代儲存的指標 **myptr**，並傳回先前儲存的指標。  
  
```   
Type *release() throw();
```  
  
### <a name="return-value"></a>傳回值  
 之前儲存的指標。  
  
### <a name="remarks"></a>備註  
 這個成員會以 Null 指標取代儲存的指標 **myptr**，並傳回先前儲存的指標。  
  
### <a name="example"></a>範例  
  
```cpp  
// auto_ptr_release.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
using namespace std;  
  
class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
##  <a name="reset"></a> auto_ptr::reset  
 成員函式會評估運算式**刪除** **myptr**，不過，只有儲存的指標值**myptr**變更函式呼叫的結果。 它接著會將儲存的指標取代為 **ptr**。  
  
```   
void reset(Type* ptr = 0);
```  
  
### <a name="parameters"></a>參數  
 `ptr`  
 此指標指定成取代儲存的指標 **myptr**。  
  
### <a name="example"></a>範例  
  
```cpp  
// auto_ptr_reset.cpp  
// compile with: /EHsc  
#include <memory>  
#include <iostream>  
#include <vector>  
  
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```  
  
```Output  
Constructing 00311AF8 Value: 5  
Constructing 00311B88 Value: 6  
Destructing 00311AF8 Value: 5  
pi2 == pi3  
Destructing 00311B88 Value: 6  
```  
  
## <a name="see-also"></a>另請參閱  
 [C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [unique_ptr 類別](../standard-library/unique-ptr-class.md)

