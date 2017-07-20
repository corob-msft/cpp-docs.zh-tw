---
title: "CAnimationTimerEventHandler 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::CreateInstance
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::OnRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationTimerEventHandler::SetAnimationController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationTimerEventHandler class
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 5412c215caf85440e923e8a083ed310f8960849a
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="canimationtimereventhandler-class"></a>CAnimationTimerEventHandler 類別
實作回呼，當發生計時事件時由動畫 API 呼叫。  
  
## <a name="syntax"></a>語法  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[CAnimationTimerEventHandler::CreateInstance](#createinstance)|建立的執行個體`CAnimationTimerEventHandler`回呼。|  
|[CAnimationTimerEventHandler::OnPostUpdate](#onpostupdate)|處理動畫更新完成之後，會發生的事件。 (覆寫 `CUIAnimationTimerEventHandlerBase::OnPostUpdate`。)|  
|[CAnimationTimerEventHandler::OnPreUpdate](#onpreupdate)|處理動畫更新開始之前發生的事件。 (覆寫 `CUIAnimationTimerEventHandlerBase::OnPreUpdate`。)|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](#onrenderingtooslow)|處理動畫呈現畫面播放速率低於最小的理想畫面播放速率時，會發生的事件。 (覆寫 `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`。)|  
|[CAnimationTimerEventHandler::SetAnimationController](#setanimationcontroller)|儲存路由事件的動畫控制器的指標。|  
  
## <a name="remarks"></a>備註  
 此事件處理常式建立並傳遞至 IUIAnimationTimer::SetTimerEventHandler，當您呼叫 CAnimationController::EnableAnimationTimerEventHandler。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## <a name="requirements"></a>需求  
 **標頭：** afxanimationcontroller.h  
  
##  <a name="createinstance"></a>CAnimationTimerEventHandler::CreateInstance  
 建立 CAnimationTimerEventHandler 回呼的執行個體。  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CAnimationController* pAnimationController,  
    IUIAnimationTimerEventHandler** ppTimerEventHandler);
```  
  
### <a name="parameters"></a>參數  
 `pAnimationController`  
 動畫控制器，將會收到事件指標。  
  
 `ppTimerEventHandler`  
  
### <a name="return-value"></a>傳回值  
 如果方法成功，它會傳回 S_OK。 否則，它會傳回 HRESULT 錯誤碼。  
  
##  <a name="onpostupdate"></a>CAnimationTimerEventHandler::OnPostUpdate  
 處理動畫更新完成之後，會發生的事件。  
  
```  
IFACEMETHOD(OnPostUpdate)();
```  
  
### <a name="return-value"></a>傳回值  
 S_OK，如果方法成功。否則 E_FAIL。  
  
##  <a name="onpreupdate"></a>CAnimationTimerEventHandler::OnPreUpdate  
 處理動畫更新開始之前發生的事件。  
  
```  
IFACEMETHOD(OnPreUpdate)();
```  
  
### <a name="return-value"></a>傳回值  
 S_OK，如果方法成功。否則 E_FAIL。  
  
##  <a name="onrenderingtooslow"></a>CAnimationTimerEventHandler::OnRenderingTooSlow  
 處理動畫呈現畫面播放速率低於最小的理想畫面播放速率時，會發生的事件。  
  
```  
IFACEMETHOD(OnRenderingTooSlow)(UINT32 fps);
```  
  
### <a name="parameters"></a>參數  
 `fps`  
  
### <a name="return-value"></a>傳回值  
 S_OK，如果方法成功。否則 E_FAIL。  
  
##  <a name="setanimationcontroller"></a>CAnimationTimerEventHandler::SetAnimationController  
 儲存路由事件的動畫控制器的指標。  
  
```  
void SetAnimationController(CAnimationController* pAnimationController);
```  
  
### <a name="parameters"></a>參數  
 `pAnimationController`  
 動畫控制器，將會收到事件指標。  
  
## <a name="see-also"></a>另請參閱  
 [類別](../../mfc/reference/mfc-classes.md)
