---
title: "bad_target 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
dev_langs:
- C++
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 145aa17b4589fb572f3b6594360ec69db5e15287
ms.contentlocale: zh-tw
ms.lasthandoff: 03/17/2017

---
# <a name="badtarget-class"></a>bad_target 類別
這個類別描述在傳訊區塊獲得目標的指標，但該目標對所執行的作業來說並不正確時，所擲回的例外狀況。  
  
## <a name="syntax"></a>語法  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[bad_target](#ctor)|多載。 建構 `bad_target` 物件。|  
  
## <a name="remarks"></a>備註  
 例如嘗試使用不同的目標保留的訊息或釋放其並未持有的保留項目為目標的原因，通常會擲回這個例外狀況。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>需求  
 **標頭︰** concrt.h  
  
 **命名空間：** concurrency  
  
##  <a name="ctor"></a>bad_target 

 建構 `bad_target` 物件。  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>參數  
 `_Message`  
 錯誤的描述性訊息。  
  
## <a name="see-also"></a>另請參閱  
 [concurrency 命名空間](concurrency-namespace.md)   
 [非同步訊息區](../../../parallel/concrt/asynchronous-message-blocks.md)



