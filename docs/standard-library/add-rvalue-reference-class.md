---
title: "add_rvalue_reference 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- type_traits/std::add_rvalue_reference
- add_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: faa8014788d12841df6a0822ec7fe379198f06d1
ms.contentlocale: zh-tw
ms.lasthandoff: 04/19/2017

---
# <a name="addrvaluereference-class"></a>add_rvalue_reference 類別
如果範本參數是物件或函式類型，請建立其右值參考類型。 否則，基於參考摺疊的語意，類型會與範本參數相同。  
  
## <a name="syntax"></a>語法  
  
```cpp  
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```  
  
#### <a name="parameters"></a>參數  
 T  
 要修改的類型。  
  
## <a name="remarks"></a>備註  
 `add_rvalue_reference` 類別具有名為 `type` 的成員，這是範本參數 `T` 之右值參考類型的別名。 參考摺疊的語意表示，針對非物件和非函式類型 `T`，`T&&` 是 `T`。 例如，`T` 是左值參考類型時，`add_rvalue_reference<T>::type` 會是左值參考類型，而非右值參考。  
  
 為了方便起見，<type_traits> 定義協助程式範本 `add_rvalue_reference_t`，以設定 `add_rvalue_reference` 之 `type` 成員的別名。  
  
## <a name="example"></a>範例  
 這個程式碼範例使用 static_assert 顯示如何使用 `add_rvalue_reference` 和 `add_rvalue_reference_t` 建立右值參考類型，以及左值參考類型上 `add_rvalue_reference`的結果不是右值參考，但摺疊到左值參考類型。  
  
```cpp  
// ex_add_rvalue_reference.cpp  
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp  
#include <type_traits>   
#include <iostream>   
#include <string>  
  
using namespace std;  
int main()  
{  
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,   
        "Expected add_rvalue_reference_t<string> to be string&&");  
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,   
        "Expected add_rvalue_reference_t<string*> to be string*&&");  
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,   
        "Expected add_rvalue_reference_t<string&> to be string&");  
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,   
        "Expected add_rvalue_reference_t<string&&> to be string&&");  
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;  
    return 0;  
}  
  
/*Output:  
All static_assert tests of add_rvalue_reference passed.  
*/  
```  
  
## <a name="requirements"></a>需求  
 標頭：<type_traits> 命名空間：std  
  
## <a name="see-also"></a>另請參閱  
 [<type_traits>](../standard-library/type-traits.md)   
 [add_lvalue_reference 類別](../standard-library/add-lvalue-reference-class.md)   
 [is_rvalue_reference 類別](../standard-library/is-rvalue-reference-class.md)
