---
title: "critical_section 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
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
ms.openlocfilehash: 58821589a4b7596b80179a77dfd6a5772531f053
ms.contentlocale: zh-tw
ms.lasthandoff: 03/17/2017

---
# <a name="criticalsection-class"></a>critical_section 類別
其為並行執行階段明確察覺且不可重新進入的 Mutex。  
  
## <a name="syntax"></a>語法  
  
```
class critical_section;
```  
  
## <a name="members"></a>Members  
  
### <a name="public-typedefs"></a>公用 Typedefs  
  
|名稱|描述|  
|----------|-----------------|  
|`native_handle_type`|對 `critical_section` 物件的參考。|  
  
### <a name="public-classes"></a>公用類別  
  
|名稱|描述|  
|----------|-----------------|  
|[critical_section 類別](#critical_section__scoped_lock_class)|例外狀況安全 RAII 包裝函式`critical_section`物件。|  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[critical_section](#ctor)|建構新的重要區段。|  
|[~ critical_section 解構函式](#dtor)|終結重要區段。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[lock](#lock)|取得此重要區段。|  
|[native_handle](#native_handle)|傳回平台特定原生控制代碼，如果存在的話。|  
|[try_lock](#try_lock)|嘗試取得鎖定，而不會封鎖。|  
|[try_lock_for](#try_lock_for)|嘗試取得鎖定，而不進行特定毫秒數的封鎖。|  
|[unlock](#unlock)|解除鎖定重要區段。|  
  
## <a name="remarks"></a>備註  
 如需詳細資訊，請參閱[同步處理資料結構](../../../parallel/concrt/synchronization-data-structures.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `critical_section`  
  
## <a name="requirements"></a>需求  
 **標頭︰** concrt.h  
  
 **命名空間：** concurrency  
  
##  <a name="ctor"></a>critical_section 

 建構新的重要區段。  
  
```
critical_section();
```  
  
##  <a name="dtor"></a>~ critical_section 

 終結重要區段。  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>備註  
 預期解構函式執行時，不會再保留鎖定。 允許重要區段的鎖定解構仍保留在未定義的行為結果。  
  
##  <a name="lock"></a>鎖定 

 取得此重要區段。  
  
```
void lock();
```  
  
### <a name="remarks"></a>備註  
 通常是安全的作法是利用[scoped_lock](#critical_section__scoped_lock_class)建構函式來取得及釋放`critical_section`物件擲回例外狀況安全的方式。  
  
 如果鎖定已保留所呼叫的內容， [improper_lock](improper-lock-class.md)擲回例外狀況。  
  
##  <a name="native_handle"></a>native_handle 

 傳回平台特定原生控制代碼，如果存在的話。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>傳回值  
 重要區段的參考。  
  
### <a name="remarks"></a>備註  
 A`critical_section`物件不是 Windows 作業系統的平台特定原生控制代碼相關聯。 此方法只會傳回物件本身的參考。  
  
##  <a name="critical_section__scoped_lock_class"></a>critical_section 類別  
 例外狀況安全 RAII 包裝函式`critical_section`物件。  
  
```
class scoped_lock;
```  
  
##  <a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock 

 建構`scoped_lock`物件，並取得`critical_section`物件傳入`_Critical_section`參數。 如果關鍵區段由另一個執行緒，這個呼叫會封鎖。  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>參數  
 `_Critical_section`  
 若要鎖定重要區段。  
  
##  <a name="critical_section__scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock 

 終結`scoped_lock`物件，並釋放其建構函式中提供的重要區段。  
  
```
~scoped_lock();
```  
  
##  <a name="try_lock"></a>try_lock 

 嘗試取得鎖定，而不會封鎖。  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>傳回值  
 如果已取得鎖定，值`true`; 否則值`false`。  
  
##  <a name="try_lock_for"></a>try_lock_for 

 嘗試取得鎖定，而不進行特定毫秒數的封鎖。  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>參數  
 `_Timeout`  
 在逾時前要等候的毫秒數。  
  
### <a name="return-value"></a>傳回值  
 如果已取得鎖定，值`true`; 否則值`false`。  
  
##  <a name="unlock"></a>解除鎖定 

 解除鎖定重要區段。  
  
```
void unlock();
```  
  
## <a name="see-also"></a>另請參閱  
 [concurrency 命名空間](concurrency-namespace.md)   
 [reader_writer_lock 類別](reader-writer-lock-class.md)
