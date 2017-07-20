---
title: "system_error 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::system_error
- system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
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
ms.openlocfilehash: cec13ab1b6358ffeb9c8df31154f5b706c266c5b
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="systemerror-class"></a>system_error 類別
代表已擲回以報告低階系統錯誤之所有例外狀況的基底類別。  
  
## <a name="syntax"></a>語法  
  
```  
class system_error : public runtime_error {  
public:  
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

 };  
```  
  
## <a name="remarks"></a>備註  
 類別 [exception](../standard-library/exception-class.md) 中 `what` 所傳回的值是從 `_Message` 和類型 [error_code](../standard-library/error-code-class.md) (可能是 `code` 或 `error_code(_Errval, _Errcat)`) 的儲存物件中所建構。  
  
 成員函式 `code` 會傳回儲存的 [error_code](../standard-library/error-code-class.md) 物件。  
  
## <a name="requirements"></a>需求  
 **標頭：**\<system_error>  
  
 **命名空間：** std  
  
## <a name="see-also"></a>另請參閱  
 [<system_error>](../standard-library/system-error.md)

