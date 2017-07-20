---
title: "is_trivially_default_constructible 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- is_trivially_default_constructible
- type_traits/std::is_trivially_default_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
caps.latest.revision: 17
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
ms.sourcegitcommit: 51fbd09793071631985720550007dddbe16f598f
ms.openlocfilehash: dd41fbdcc33250bc60a0b919b17dd52862549a77
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="istriviallydefaultconstructible-class"></a>is_trivially_default_constructible 類別
測試類型是否有 trivial 預設建構函式。  
  
## <a name="syntax"></a>語法  
  
```
template <class Ty>
struct is_trivially_default_constructible;
```  
  
#### <a name="parameters"></a>參數  
 `Ty`  
 要查詢的類型。  
  
## <a name="remarks"></a>備註  
 如果 `Ty` 類型是具有 trivial 建構函式的類別，則類型述詞的執行個體保留 true，否則保留 false。  
  
 在下列情況下，類別 `Ty` 的預設建構函式是 trivial：  
  
-   它是以隱含方式宣告的預設建構函式  
  
-   類別 `Ty` 沒有虛擬函式  
  
-   類別 `Ty` 沒有虛擬基底  
  
-   類別 `Ty` 的所有直接基底都有 trivial 建構函式  
  
-   類別類型的所有非靜態資料成員的類別都具有 trivial 建構函式  
  
-   類別的類型陣列的所有非靜態資料成員的類別，都具有 trivial 建構函式  
  
## <a name="requirements"></a>需求  
 **標頭：**\<type_traits>  
  
 **命名空間：** std  
  
## <a name="see-also"></a>另請參閱  
 [<type_traits>](../standard-library/type-traits.md)



