---
title: "IProvideClassInfo2Impl 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::IProvideClassInfo2Impl
- ATLCOM/ATL::IProvideClassInfo2Impl::GetClassInfo
- ATLCOM/ATL::IProvideClassInfo2Impl::GetGUID
- ATLCOM/ATL::IProvideClassInfo2Impl::_tih
dev_langs:
- C++
helpviewer_keywords:
- IProvideClassInfo2Impl class
- IProvideClassInfo2 ATL implementation
- class information, ATL
ms.assetid: d74956e8-9c69-4cba-b99d-ca1ac031bb9d
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 0d3bed0f625e396b63ada19ded02ba9ad3b697b0
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="iprovideclassinfo2impl-class"></a>IProvideClassInfo2Impl 類別
這個類別提供的預設實作[IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303)和[IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764)方法。  
  
## <a name="syntax"></a>語法  
  
```
template <const CLSID* pcoclsid,
    const IID* psrcid,
    const GUID* plibid = &CAtlModule::m_libid,
    WORD wMajor = 1,
    WORD wMinor = 0, class tihclass = CComTypeInfoHolder>  
class ATL_NO_VTABLE IProvideClassInfo2Impl : public IProvideClassInfo2
```  
  
#### <a name="parameters"></a>參數  
 *pcoclsid*  
 Coclass 的識別碼指標。  
  
 *psrcid*  
 Coclass 的預設的傳出分配介面的識別碼指標。  
  
 `plibid`  
 包含介面的相關資訊的型別程式庫的 LIBID 指標。 根據預設，會傳遞伺服器層級類型程式庫。  
  
 `wMajor`  
 型別程式庫的主要版本。 預設值為 1。  
  
 `wMinor`  
 次要類型程式庫版本。 預設值為 0。  
  
 `tihclass`  
 用來管理 coclass 的型別資訊的類別。 預設值是 `CComTypeInfoHolder`。  
  
## <a name="members"></a>Members  
  
### <a name="constructors"></a>建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::IProvideClassInfo2Impl](#iprovideclassinfo2impl)|建構函式。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::GetClassInfo](#getclassinfo)|擷取**ITypeInfo** coclass 的型別資訊的指標。|  
|[IProvideClassInfo2Impl::GetGUID](#getguid)|擷取物件的外寄的分配介面的 GUID。|  
  
### <a name="protected-data-members"></a>受保護的資料成員  
  
|名稱|說明|  
|----------|-----------------|  
|[IProvideClassInfo2Impl::_tih](#_tih)|管理 coclass 的型別資訊。|  
  
## <a name="remarks"></a>備註  
 [IProvideClassInfo2](http://msdn.microsoft.com/library/windows/desktop/ms693764)介面會擴充[IProvideClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms687303)加`GetGUID`方法。 此方法可讓用戶端擷取物件的輸出介面 IID，其預設事件集。 類別`IProvideClassInfo2Impl`提供的預設實作**IProvideClassInfo**和`IProvideClassInfo2`方法。  
  
 `IProvideClassInfo2Impl`包含型別的靜態成員`CComTypeInfoHolder`管理 coclass 的型別資訊。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `IProvideClassInfo2`  
  
 `IProvideClassInfo2Impl`  
  
## <a name="requirements"></a>需求  
 **標頭︰**於 atlcom.h  
  
##  <a name="getclassinfo"></a>IProvideClassInfo2Impl::GetClassInfo  
 擷取`ITypeInfo`coclass 的型別資訊的指標。  
  
```
STDMETHOD(GetClassInfo)(ITypeInfo** pptinfo);
```  
  
### <a name="remarks"></a>備註  
 請參閱[IProvideClassInfo::GetClassInfo](http://msdn.microsoft.com/library/windows/desktop/ms690192)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="getguid"></a>IProvideClassInfo2Impl::GetGUID  
 擷取物件的外寄的分配介面的 GUID。  
  
```
STDMETHOD(GetGUID)(
    DWORD dwGuidKind,
    GUID* pGUID);
```  
  
### <a name="remarks"></a>備註  
 請參閱[IProvideClassInfo2::GetGUID](http://msdn.microsoft.com/library/windows/desktop/ms679721)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="iprovideclassinfo2impl"></a>IProvideClassInfo2Impl::IProvideClassInfo2Impl  
 建構函式。  
  
```
IProvideClassInfo2Impl();
```  
  
### <a name="remarks"></a>備註  
 呼叫`AddRef`上[_tih](#_tih)成員。 解構函式呼叫**版本**。  
  
##  <a name="_tih"></a>IProvideClassInfo2Impl::_tih  
 這個靜態資料成員是類別樣板參數的執行個體`tihclass`，其預設值是`CComTypeInfoHolder`。  
  
```
static  tihclass
    _tih;
```     
  
### <a name="remarks"></a>備註  
 `_tih`管理 coclass 的型別資訊。  
  
## <a name="see-also"></a>另請參閱  
 [類別概觀](../../atl/atl-class-overview.md)
