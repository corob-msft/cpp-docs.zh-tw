---
title: "SyncLockWithStatusT 類別 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SyncLockWithStatusT 類別"
ms.assetid: 4832fd93-0ac8-4168-9404-b43fefea7476
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# SyncLockWithStatusT 類別
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

支援 WRL 結構，而且不能直接從您的程式碼使用。  
  
## <a name="syntax"></a>語法  
  
```  
template <  
   typename SyncTraits  
>  
class SyncLockWithStatusT : public SyncLockT<SyncTraits>;  
```  
  
#### <a name="parameters"></a>參數  
 `SyncTraits`  
 型別，可以採取獨佔或共用資源的擁有權。  
  
## <a name="remarks"></a>備註  
 表示型別可以採取獨佔或共用資源的擁有權。  
  
 SyncLockWithStatusT 類別用來實作 [Mutex](../windows/mutex-class1.md) 和 [號誌](../windows/semaphore-class.md) 類別。  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[Synclockwithstatust:: Synclockwithstatust 建構函式](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|初始化 SyncLockWithStatusT 類別的新執行個體。|  
  
### <a name="protected-constructors"></a>受保護的建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[Synclockwithstatust:: Synclockwithstatust 建構函式](../windows/synclockwithstatust-synclockwithstatust-constructor.md)|初始化 SyncLockWithStatusT 類別的新執行個體。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[Synclockwithstatust:: Getstatus 方法](../windows/synclockwithstatust-getstatus-method.md)|擷取目前的 SyncLockWithStatusT 物件的等候狀態。|  
|[Synclockwithstatust:: Islocked 方法](../windows/synclockwithstatust-islocked-method.md)|指出目前的 SyncLockWithStatusT 物件是否擁有資源。亦即，SyncLockWithStatusT 物件是 *鎖定*。|  
  
### <a name="protected-data-members"></a>受保護的資料成員  
  
|名稱|說明|  
|----------|-----------------|  
|[Synclockwithstatust:: Status_ 資料成員](../windows/synclockwithstatust-status-data-member.md)|物件根據目前的 SyncLockWithStatusT 物件保存結果的基礎等待鎖定作業之後的作業。|  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `SyncLockT`  
  
 `SyncLockWithStatusT`  
  
## <a name="requirements"></a>需求  
 **標頭︰** corewrappers.h  
  
 **命名空間︰** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>另請參閱  
 [Microsoft::WRL::Wrappers::Details 命名空間](../windows/microsoft-wrl-wrappers-details-namespace.md)