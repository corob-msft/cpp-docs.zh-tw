---
title: "CAnimationColor 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::CAnimationColor
- AFXANIMATIONCONTROLLER/CAnimationColor::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationColor::GetB
- AFXANIMATIONCONTROLLER/CAnimationColor::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetG
- AFXANIMATIONCONTROLLER/CAnimationColor::GetR
- AFXANIMATIONCONTROLLER/CAnimationColor::GetValue
- AFXANIMATIONCONTROLLER/CAnimationColor::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationColor::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationColor::m_bValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_gValue
- AFXANIMATIONCONTROLLER/CAnimationColor::m_rValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationColor class
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: 17
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
ms.openlocfilehash: e053986737b8e62103666787b99b01cbf19cdc60
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="canimationcolor-class"></a>CAnimationColor 類別
實作紅色、綠色和藍色元件可以動畫顯示的色彩功能。  
  
## <a name="syntax"></a>語法  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](#canimationcolor)|多載。 建構的動畫色彩物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](#addtransition)|新增轉換為紅色、 綠色和藍色元件。|  
|[CAnimationColor::GetB](#getb)|提供存取權 CAnimationVariable 代表藍色元件。|  
|[CAnimationColor::GetDefaultValue](#getdefaultvalue)|傳回元件的預設值。|  
|[CAnimationColor::GetG](#getg)|提供存取權 CAnimationVariable 代表綠色的元件。|  
|[CAnimationColor::GetR](#getr)|提供存取權 CAnimationVariable 代表紅色的元件。|  
|[CAnimationColor::GetValue](#getvalue)|傳回目前的值。|  
|[CAnimationColor::SetDefaultValue](#setdefaultvalue)|設定預設值。|  
  
### <a name="protected-methods"></a>受保護的方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](#getanimationvariablelist)|將封裝的動畫變數放入清單。 (覆寫[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。)|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](#operator_colorref)||  
|[CAnimationColor::operator =](#operator_eq)|將色彩指派給 CAnimationColor。|  
  
### <a name="protected-data-members"></a>受保護的資料成員  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationColor::m_bValue](#m_bvalue)|表示動畫色彩的藍色元件之封裝的動畫變數。|  
|[CAnimationColor::m_gValue](#m_gvalue)|表示動畫色彩的綠色元件之封裝的動畫變數。|  
|[CAnimationColor::m_rValue](#m_rvalue)|表示動畫色彩的紅色元素之封裝的動畫變數。|  
  
## <a name="remarks"></a>備註  
 CAnimationColor 類別包含三個 CAnimationVariable 物件，而色彩應用程式中可以表示。 例如，您可以使用這個類別，以動畫顯示在螢幕上的任何物件的色彩 （例如文字色彩背景色彩等等）。 若要在應用程式中使用這個類別，只要具現化這個類別的物件、 將它新增至使用 CAnimationController::AddAnimationObject 動畫控制器，並呼叫每個轉換的還得再套用到紅色、 綠色和藍色元件。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationColor`  
  
## <a name="requirements"></a>需求  
 **標頭：** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationColor::AddTransition  
 新增轉換為紅色、 綠色和藍色元件。  
  
```  
void AddTransition(
    CBaseTransition* pRTransition,  
    CBaseTransition* pGTransition,  
    CBaseTransition* pBTransition);
```  
  
### <a name="parameters"></a>參數  
 `pRTransition`  
 紅元件的轉換。  
  
 `pGTransition`  
 綠元件的轉換。  
  
 `pBTransition`  
 藍元件的轉換。  
  
### <a name="remarks"></a>備註  
 呼叫此函式可將指定的轉換加入至轉換套用至動畫變數表示色彩元件的內部清單。 當您新增的轉換時，它們就會不會立即套用，並儲存在內部清單。 轉換會套用 （加入至腳本，以尋找特定的值） 當您呼叫 CAnimationController::AnimateGroup。 如果您不需要將轉換套用到其中一個色彩元件，您可以傳遞 NULL。  
  
##  <a name="canimationcolor"></a>CAnimationColor::CAnimationColor  
 建構 CAnimationColor 物件。  
  
```  
CAnimationColor();
 
CAnimationColor(
    COLORREF color,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>參數  
 `color`  
 指定預設色彩。  
  
 `nGroupID`  
 指定群組識別碼。  
  
 `nObjectID`  
 指定物件識別碼。  
  
 `dwUserData`  
 指定使用者定義的資料。  
  
### <a name="remarks"></a>備註  
 預設值為紅色、 綠色、 藍色，物件識別碼和群組識別碼，這將會設定為 0，建構的物件。 它們都可以在執行階段使用 SetDefaultValue 和 SetID 之後變更。  
  
##  <a name="getanimationvariablelist"></a>CAnimationColor::GetAnimationVariableList  
 將封裝的動畫變數放入清單。  
  
```  
virtual void GetAnimationVariableList(CList<CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>參數  
 `lst`  
 函式傳回時，它會包含代表紅色、 綠色和藍色元件的三個 CAnimationVariable 物件的指標。  
  
##  <a name="getb"></a>CAnimationColor::GetB  
 提供存取權 CAnimationVariable 代表藍色元件。  
  
```  
CAnimationVariable& GetB();
```  
  
### <a name="return-value"></a>傳回值  
 封裝 CAnimationVariable 代表藍色元件參考。  
  
### <a name="remarks"></a>備註  
 您可以呼叫這個方法，以直接存取基礎 CAnimationVariable 代表藍色元件。  
  
##  <a name="getdefaultvalue"></a>CAnimationColor::GetDefaultValue  
 傳回元件的預設值。  
  
```  
COLORREF GetDefaultValue();
```  
  
### <a name="return-value"></a>傳回值  
 COLORREF 值，包含 RGB 元件的預設值。  
  
### <a name="remarks"></a>備註  
 呼叫此函式可擷取先前已設定的建構函式或 SetDefaultValue 的預設值。  
  
##  <a name="getg"></a>CAnimationColor::GetG  
 提供存取權 CAnimationVariable 代表綠色的元件。  
  
```  
CAnimationVariable& GetG();
```  
  
### <a name="return-value"></a>傳回值  
 封裝 CAnimationVariable 代表綠色元件的參考。  
  
### <a name="remarks"></a>備註  
 您可以呼叫這個方法，以直接存取基礎 CAnimationVariable 代表綠色元件。  
  
##  <a name="getr"></a>CAnimationColor::GetR  
 提供存取權 CAnimationVariable 代表紅色的元件。  
  
```  
CAnimationVariable& GetR();
```  
  
### <a name="return-value"></a>傳回值  
 封裝 CAnimationVariable 代表紅色元件參考。  
  
### <a name="remarks"></a>備註  
 您可以呼叫這個方法，以直接存取基礎 CAnimationVariable 代表紅色的元件。  
  
##  <a name="getvalue"></a>CAnimationColor::GetValue  
 傳回目前的值。  
  
```  
BOOL GetValue(COLORREF& color);
```  
  
### <a name="parameters"></a>參數  
 `color`  
 輸出。 這個方法傳回時，包含目前的值。  
  
### <a name="return-value"></a>傳回值  
 如果為 TRUE，已順利擷取目前的值。否則為 FALSE。  
  
### <a name="remarks"></a>備註  
 呼叫此函式以擷取動畫色彩的目前值。 如果此方法失敗或色彩元件的基礎 COM 物件尚未初始化，色彩會包含建構函式中或 SetDefaultValue 先前設定的預設值。  
  
##  <a name="m_bvalue"></a>CAnimationColor::m_bValue  
 表示動畫色彩的藍色元件之封裝的動畫變數。  
  
```  
CAnimationVariable m_bValue;  
```  
  
##  <a name="m_gvalue"></a>CAnimationColor::m_gValue  
 表示動畫色彩的綠色元件之封裝的動畫變數。  
  
```  
CAnimationVariable m_gValue;  
```  
  
##  <a name="m_rvalue"></a>CAnimationColor::m_rValue  
 表示動畫色彩的紅色元素之封裝的動畫變數。  
  
```  
CAnimationVariable m_rValue;  
```  
  
##  <a name="operator_colorref"></a>CAnimationColor::operator COLORREF  
  
```  
operator COLORREF();
```   
  
### <a name="return-value"></a>傳回值  
  
##  <a name="operator_eq"></a>CAnimationColor::operator =  
 將色彩指派給 CAnimationColor。  
  
```  
void operator=(COLORREF color);
```  
  
### <a name="parameters"></a>參數  
 `color`  
 指定新值動畫色彩。  
  
### <a name="remarks"></a>備註  
 建議您這麼做之前動畫開始這個運算子會呼叫 SetDefaultValue，重新建立色彩元件的基礎 COM 物件，如果已建立。 如果您已訂閱事件 （ValueChanged 或 IntegerValueChanged） 這個動畫物件，您需要重新啟用這些事件。  
  
##  <a name="setdefaultvalue"></a>CAnimationColor::SetDefaultValue  
 設定預設值。  
  
```  
void SetDefaultValue(COLORREF color);
```  
  
### <a name="parameters"></a>參數  
 `color`  
 指定新的預設值為紅色、 綠色和藍色元件。  
  
### <a name="remarks"></a>備註  
 使用此函式將預設值為動畫物件。 這個方法會將預設值指派給動畫色彩的色彩元件。 如果尚未建立，它也會建立基礎 COM 物件。 如果您已訂閱事件 （ValueChanged 或 IntegerValueChanged） 這個動畫物件，您需要重新啟用這些事件。  
  
## <a name="see-also"></a>另請參閱  
 [類別](../../mfc/reference/mfc-classes.md)
