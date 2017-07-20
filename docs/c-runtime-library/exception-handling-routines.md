---
title: "例外狀況處理常式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.exceptions
dev_langs:
- C++
helpviewer_keywords:
- exception handling, routines
ms.assetid: f60548c6-850a-4e1e-a79b-a2a6a541ab62
caps.latest.revision: 8
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 3dd5d8dd77f2b62a6b0ea52e7d056b3d779cd2f4
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="exception-handling-routines"></a>例外狀況處理常式
使用 C++ 例外狀況處理函式在程式執行期間從非預期的事件復原。  
  
### <a name="exception-handling-functions"></a>例外狀況處理函式  
  
|函式|用法|  
|--------------|---------|  
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|以 C++ 類型化例外狀況處理 Win32 例外狀況 (C 結構化例外狀況)|  
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|安裝要由 `terminate` 呼叫的專屬終止常式|  
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|安裝要由 `unexpected` 呼叫的專屬終止函式|  
|[terminate](../c-runtime-library/reference/terminate-crt.md)|在擲回例外狀況之後，在某些情況下自動呼叫。 `terminate` 函式會呼叫 `abort` 或您使用 `set_terminate` 指定的函式|  
|[unexpected](../c-runtime-library/reference/unexpected-crt.md)|呼叫 `terminate` 或您使用 `set_unexpected` 指定的函式。 目前 Microsoft C++ 例外狀況處理實作中未使用 `unexpected`|  
  
## <a name="see-also"></a>另請參閱  
 [依類別區分的執行階段常式](../c-runtime-library/run-time-routines-by-category.md)