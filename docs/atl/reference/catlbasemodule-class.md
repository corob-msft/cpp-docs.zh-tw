---
title: "CAtlBaseModule 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
dev_langs:
- C++
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 4897f6cf7e12a18401720ad663c90491bb0e599d
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="catlbasemodule-class"></a>CAtlBaseModule 類別
這個類別具現化每個 ATL 專案中。  
  
## <a name="syntax"></a>語法  
  
```
class CAtlBaseModule : public _ATL_BASE_MODULE
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|建構函式。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|將資源執行個體加入至預存的控制代碼的清單。|  
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|傳回指定的資源執行個體的控制代碼。|  
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|傳回從模組執行個體`CAtlBaseModule`物件。|  
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|傳回資源執行個體從`CAtlBaseModule`物件。|  
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|從預存的控制代碼的清單中移除資源的執行個體。|  
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|設定的資源執行個體`CAtlBaseModule`物件。|  
  
### <a name="public-data-members"></a>公用資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|[CAtlBaseModule::m_bInitFailed](#m_binitfailed)|變數，指出是否模組初始化失敗。|  
  
## <a name="remarks"></a>備註  
 執行個體`CAtlBaseModule`具名的 _AtlBaseModule 存在於每個包含模組的執行個體的控制代碼，包含資源 （在預設狀況下都是同一個） 的模組和模組提供主要的資源控制代碼陣列的控制代碼的 ATL 專案。 `CAtlBaseModule`可以安全地從多個執行緒存取。  
  
 這個類別會取代過時[CComModule](../../atl/reference/ccommodule-class.md)用在舊版的 ATL 類別  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)  
  
 `CAtlBaseModule`  
  
## <a name="requirements"></a>需求  
 **標頭︰** atlcore.h  
  
##  <a name="addresourceinstance"></a>CAtlBaseModule::AddResourceInstance  
 將資源執行個體加入至預存的控制代碼的清單。  
  
```
bool AddResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>參數  
 `hInst`  
 若要新增為資源執行個體。  
  
### <a name="return-value"></a>傳回值  
 如果資源已成功則傳回 true，加入 false 否則。  
  
##  <a name="catlbasemodule"></a>CAtlBaseModule::CAtlBaseModule  
 建構函式。  
  
```
CAtlBaseModule() throw();
```  
  
### <a name="remarks"></a>備註  
 建立 `CAtlBaseModule`。  
  
##  <a name="gethinstanceat"></a>CAtlBaseModule::GetHInstanceAt  
 傳回指定的資源執行個體的控制代碼。  
  
```
HINSTANCE GetHInstanceAt(int i) throw();
```  
  
### <a name="parameters"></a>參數  
 *i*  
 資源執行個體的數目。  
  
### <a name="return-value"></a>傳回值  
 如果沒有對應的資源執行個體，傳回的控制代碼資源的執行個體，或 NULL。  
  
##  <a name="getmoduleinstance"></a>CAtlBaseModule::GetModuleInstance  
 傳回從模組執行個體`CAtlBaseModule`物件。  
  
```
HINSTANCE GetModuleInstance() throw();
```  
  
### <a name="return-value"></a>傳回值  
 傳回模組的執行個體。  
  
##  <a name="getresourceinstance"></a>CAtlBaseModule::GetResourceInstance  
 傳回的資源執行個體。  
  
```
HINSTANCE GetResourceInstance() throw();
```  
  
### <a name="return-value"></a>傳回值  
 傳回的資源執行個體。  
  
##  <a name="m_binitfailed"></a>CAtlBaseModule::m_bInitFailed  
 變數，指出是否模組初始化失敗。  
  
```
static bool m_bInitFailed;
```  
  
### <a name="remarks"></a>備註  
 如果模組初始化，false 如果它無法初始化，則為 true。  
  
##  <a name="removeresourceinstance"></a>CAtlBaseModule::RemoveResourceInstance  
 從預存的控制代碼的清單中移除資源的執行個體。  
  
```
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>參數  
 `hInst`  
 若要移除資源執行個體。  
  
### <a name="return-value"></a>傳回值  
 如果資源程式已成功移除，則為 false，則傳回 true。  
  
##  <a name="setresourceinstance"></a>CAtlBaseModule::SetResourceInstance  
 設定的資源執行個體`CAtlBaseModule`物件。  
  
```
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```  
  
### <a name="parameters"></a>參數  
 `hInst`  
 新的資源執行個體。  
  
### <a name="return-value"></a>傳回值  
 傳回更新的資源執行個體。  
  
## <a name="see-also"></a>另請參閱  
 [類別概觀](../../atl/atl-class-overview.md)   
 [模組類別](../../atl/atl-module-classes.md)
