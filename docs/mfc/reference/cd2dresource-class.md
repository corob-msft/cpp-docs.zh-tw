---
title: "CD2DResource 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DResource
- AFXRENDERTARGET/CD2DResource
- AFXRENDERTARGET/CD2DResource::CD2DResource
- AFXRENDERTARGET/CD2DResource::Create
- AFXRENDERTARGET/CD2DResource::Destroy
- AFXRENDERTARGET/CD2DResource::IsValid
- AFXRENDERTARGET/CD2DResource::IsAutoDestroy
- AFXRENDERTARGET/CD2DResource::ReCreate
- AFXRENDERTARGET/CD2DResource::m_bIsAutoDestroy
- AFXRENDERTARGET/CD2DResource::m_pParentTarget
dev_langs:
- C++
helpviewer_keywords:
- CD2DResource [MFC], CD2DResource
- CD2DResource [MFC], Create
- CD2DResource [MFC], Destroy
- CD2DResource [MFC], IsValid
- CD2DResource [MFC], IsAutoDestroy
- CD2DResource [MFC], ReCreate
- CD2DResource [MFC], m_bIsAutoDestroy
- CD2DResource [MFC], m_pParentTarget
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: b292bf680a146d730554c56c60df9a649b670ba3
ms.contentlocale: zh-tw
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dresource-class"></a>CD2DResource 類別
抽象類別，提供介面來建立及管理 D2D 資源，例如筆刷、 圖層和文字。  
  
## <a name="syntax"></a>語法  
  
```  
class CD2DResource : public CObject;  
```  
  
## <a name="members"></a>成員  
  
### <a name="protected-constructors"></a>受保護的建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CD2DResource::CD2DResource](#cd2dresource)|建構 CD2DResource 物件。|  
|[CD2DResource:: ~ CD2DResource](#cd2dresource__~cd2dresource)|解構函式。 D2D 資源物件終結時呼叫。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CD2DResource::Create](#create)|建立 CD2DResource。|  
|[CD2DResource::Destroy](#destroy)|CD2DResource 物件已遭終結。|  
|[CD2DResource::IsValid](#isvalid)|檢查資源的有效性|  
  
### <a name="protected-methods"></a>受保護的方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CD2DResource::IsAutoDestroy](#isautodestroy)|核取自動終結旗標。|  
|[CD2DResource::ReCreate](#recreate)|CD2DResource 會重新建立。|  
  
### <a name="protected-data-members"></a>受保護的資料成員  
  
|名稱|說明|  
|----------|-----------------|  
|[CD2DResource::m_bIsAutoDestroy](#m_bisautodestroy)|資源將會破壞擁有者 (CRenderTarget)|  
|[CD2DResource::m_pParentTarget](#m_pparenttarget)|父 CRenderTarget 指標）|  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CD2DResource`  
  
## <a name="requirements"></a>需求  
 **標頭：** afxrendertarget.h  
  
##  <a name="_dtorcd2dresource"></a>CD2DResource:: ~ CD2DResource  
 解構函式。 D2D 資源物件終結時呼叫。  
  
```  
virtual ~CD2DResource();
```  
  
##  <a name="cd2dresource"></a>CD2DResource::CD2DResource  
 建構 CD2DResource 物件。  
  
```  
CD2DResource(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy);
```  
  
### <a name="parameters"></a>參數  
 `pParentTarget`  
 呈現目標指標。  
  
 `bAutoDestroy`  
 表示擁有者 (pParentTarget) 將會終結物件。  
  
##  <a name="create"></a>CD2DResource::Create  
 建立 CD2DResource。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget) = 0;  
```  
  
### <a name="parameters"></a>參數  
 `pRenderTarget`  
 呈現目標指標。  
  
### <a name="return-value"></a>傳回值  
 如果此方法成功，它會傳回 S_OK。 否則，它會傳回 HRESULT 錯誤碼。  
  
##  <a name="destroy"></a>CD2DResource::Destroy  
 CD2DResource 物件已遭終結。  
  
```  
virtual void Destroy() = 0;  
```  
  
##  <a name="isautodestroy"></a>CD2DResource::IsAutoDestroy  
 核取自動終結旗標。  
  
```  
BOOL IsAutoDestroy() const;  
```  
  
### <a name="return-value"></a>傳回值  
 如果將由其擁有者; 終結物件，則為 TRUE。否則為 FALSE。  
  
##  <a name="isvalid"></a>CD2DResource::IsValid  
 檢查資源的有效性  
  
```  
virtual BOOL IsValid() const = 0;  
```  
  
### <a name="return-value"></a>傳回值  
 如果資源有效，則為 TRUE否則為 FALSE。  
  
##  <a name="m_bisautodestroy"></a>CD2DResource::m_bIsAutoDestroy  
 資源將會破壞擁有者 (CRenderTarget)  
  
```  
BOOL m_bIsAutoDestroy;  
```  
  
##  <a name="m_pparenttarget"></a>CD2DResource::m_pParentTarget  
 父 CRenderTarget 指標）  
  
```  
CRenderTarget* m_pParentTarget;  
```  
  
##  <a name="recreate"></a>CD2DResource::ReCreate  
 CD2DResource 會重新建立。  
  
```  
virtual HRESULT ReCreate(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>參數  
 `pRenderTarget`  
 呈現目標指標。  
  
### <a name="return-value"></a>傳回值  
 如果此方法成功，它會傳回 S_OK。 否則，它會傳回 HRESULT 錯誤碼。  
  
## <a name="see-also"></a>另請參閱  
 [類別](../../mfc/reference/mfc-classes.md)
