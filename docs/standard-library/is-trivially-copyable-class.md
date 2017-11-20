---
title: "is_trivially_copyable 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: bf4387901e53dee51ae3c700a756358c63f8631a
ms.contentlocale: zh-tw
ms.lasthandoff: 10/03/2017

---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable 類別
測試類型是否是可透過極簡方式複製的類型。  
  
## <a name="syntax"></a>語法  
  
```
template <class T>
struct is_trivially_copyable;
```  
  
#### <a name="parameters"></a>參數  
 `T`  
 要查詢的類型。  
  
## <a name="remarks"></a>備註  
 如果類型 `T` 是可透過極簡方式複製的類型，類型述詞執行個體的值就會是 true，否則會是 false。 可透過極簡方式複製的類型沒有任何非極簡的複製作業、移動作業或解構函式。 一般而言，如果能以位元複製方式實作複製作業，該複製作業即可視為極簡。 內建類型和可透過極簡方式複製的類型陣列，都是可透過極簡方式複製的類型。  
  
## <a name="requirements"></a>需求  
 **標頭：**\<type_traits>  
  
 **命名空間：** std  
  
## <a name="see-also"></a>另請參閱  
 [<type_traits>](../standard-library/type-traits.md)



