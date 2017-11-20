---
title: "&lt;new&gt; 函式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
caps.latest.revision: 10
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 6ce4e11a41f199d4ec82a593b53c2f0b7f1c47e4
ms.contentlocale: zh-tw
ms.lasthandoff: 10/03/2017

---
# <a name="ltnewgt-functions"></a>&lt;new&gt; 函式
|||  
|-|-|  
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|  
  
##  <a name="nothrow"></a>  nothrow  
 為 **new** 和 **delete** 的 `nothrow` 版本提供要用來作為引數的物件。  
  
```  
extern const std::nothrow_t nothrow;  
```  
  
### <a name="remarks"></a>備註  
 此物件是用來作為函式引數，以符合參數類型 [std::nothrow_t](../standard-library/nothrow-t-structure.md)。  
  
### <a name="example"></a>範例  
  如需如何使用 `std::nothrow_t` 作為函式參數的範例，請參閱 [operator new](../standard-library/new-operators.md#op_new) 和 [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr)。  
  
##  <a name="set_new_handler"></a>  set_new_handler  
 安裝要在 `operator new` 嘗試配置記憶體失敗時呼叫的使用者函式。  
  
```  
new_handler set_new_handler(new_handler Pnew) throw();
```  
  
### <a name="parameters"></a>參數  
 `Pnew`  
 要安裝的 new_handler。  
  
### <a name="return-value"></a>傳回值  
 第一次呼叫時，會傳回 0，後續呼叫時，則傳回前一個 `new_handler`。  
  
### <a name="remarks"></a>備註  
 此函式會在它所維護的靜態[新處理常式](../standard-library/new-typedefs.md#new_handler)指標中儲存 `Pnew`，然後傳回先前在該指標中儲存的值。 新處理常式會由 [operator new](../standard-library/new-operators.md#op_new)( **size_t**) 使用。  
  
### <a name="example"></a>範例  
  
```cpp  
// new_set_new_handler.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
  
using namespace std;  
void __cdecl newhandler( )  
{  
   cout << "The new_handler is called:" << endl;  
   throw bad_alloc( );  
   return;  
}  
  
int main( )   
{  
   set_new_handler (newhandler);  
   try  
   {  
      while ( 1 )   
      {  
         new int[5000000];  
         cout << "Allocating 5000000 ints." << endl;  
      }  
   }  
   catch ( exception e )  
   {  
      cout << e.what( ) << endl;  
   }  
}  
```  
  
```Output  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
Allocating 5000000 ints.  
The new_handler is called:  
bad allocation  
```  
  
## <a name="see-also"></a>另請參閱  
 [\<new>](../standard-library/new.md)

