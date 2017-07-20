---
title: "CAnimationSize 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::CAnimationSize
- AFXANIMATIONCONTROLLER/CAnimationSize::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCX
- AFXANIMATIONCONTROLLER/CAnimationSize::GetCY
- AFXANIMATIONCONTROLLER/CAnimationSize::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetValue
- AFXANIMATIONCONTROLLER/CAnimationSize::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationSize::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cxValue
- AFXANIMATIONCONTROLLER/CAnimationSize::m_cyValue
dev_langs:
- C++
helpviewer_keywords:
- CAnimationSize class
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
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
ms.sourcegitcommit: 73410ae17465880f455e5b15026f6cc010803c19
ms.openlocfilehash: 84b9ae3b81f72f6c0ae8e88f78357c29e8d82ffd
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="canimationsize-class"></a>CAnimationSize 類別
實作可以動畫顯示其維度的大小物件功能。  
  
## <a name="syntax"></a>語法  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](#canimationsize)|多載。 建構的動畫大小的物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](#addtransition)|新增轉換寬度和高度。|  
|[CAnimationSize::GetCX](#getcx)|提供存取權 CAnimationVariable 代表寬度。|  
|[CAnimationSize::GetCY](#getcy)|提供存取權 CAnimationVariable 代表高度。|  
|[CAnimationSize::GetDefaultValue](#getdefaultvalue)|傳回預設值，寬度和高度。|  
|[CAnimationSize::GetValue](#getvalue)|傳回目前的值。|  
|[CAnimationSize::SetDefaultValue](#setdefaultvalue)|設定預設值。|  
  
### <a name="protected-methods"></a>受保護的方法  
  
|名稱|描述|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](#getanimationvariablelist)|將封裝的動畫變數放入清單。 (覆寫[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。)|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](#operator_csize)|將 CSize CAnimationSize。|  
|[CAnimationSize::operator =](#operator_eq)|指派 CAnimationSize szSrc。|  
  
### <a name="protected-data-members"></a>受保護的資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|[CAnimationSize::m_cxValue](#m_cxvalue)|表示動畫大小的寬度封裝的動畫變數。|  
|[CAnimationSize::m_cyValue](#m_cyvalue)|表示動畫大小的高度封裝的動畫變數。|  
  
## <a name="remarks"></a>備註  
 CAnimationSize 類別封裝兩個 CAnimationVariable 物件，並可以代表中應用程式的大小。 比方說，您可以使用這個類別，以動畫顯示的任何兩個大小，螢幕上的維度物件 (如矩形，控制等)。 若要在應用程式中使用這個類別，只要具現化這個類別的物件、 將它新增至使用 CAnimationController::AddAnimationObject 動畫控制器，並呼叫還得針對每個轉換套用至寬度或高度。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationSize` 
  
## <a name="requirements"></a>需求  
 **標頭：** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>CAnimationSize::AddTransition  
 新增轉換寬度和高度。  
  
```  
void AddTransition(
    CBaseTransition* pCXTransition,  
    CBaseTransition* pCYTransition);
```  
  
### <a name="parameters"></a>參數  
 `pCXTransition`  
 轉換寬度的指標。  
  
 `pCYTransition`  
 指標轉換為高度。  
  
### <a name="remarks"></a>備註  
 呼叫此函式可加入內部清單的轉換套用至動畫變數的寬度和高度指定的轉換。 當您新增的轉換時，它們就會不會立即套用，並儲存在內部清單。 轉換會套用 （加入至腳本，以尋找特定的值） 當您呼叫 CAnimationController::AnimateGroup。 如果您不需要將轉換套用到其中一個維度，您可以傳遞 NULL。  
  
##  <a name="canimationsize"></a>CAnimationSize::CAnimationSize  
 建構的動畫大小的物件。  
  
```  
CAnimationSize();

 
CAnimationSize(
    const CSize& szDefault,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>參數  
 `szDefault`  
 指定預設大小。  
  
 `nGroupID`  
 指定群組識別碼。  
  
 `nObjectID`  
 指定物件識別碼。  
  
 `dwUserData`  
 指定使用者定義的資料。  
  
### <a name="remarks"></a>備註  
 在建構物件的寬度、 高度，預設值的物件識別碼和群組識別碼，這將會設定為 0。 它們都可以在執行階段使用 SetDefaultValue 和 SetID 之後變更。  
  
##  <a name="getanimationvariablelist"></a>CAnimationSize::GetAnimationVariableList  
 將封裝的動畫變數放入清單。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>參數  
 `lst`  
 函式傳回時，它會包含代表寬度與高度的兩個 CAnimationVariable 物件的指標。  
  
##  <a name="getcx"></a>CAnimationSize::GetCX  
 提供存取權 CAnimationVariable 代表寬度。  
  
```  
CAnimationVariable& GetCX();
```  
  
### <a name="return-value"></a>傳回值  
 參考封裝 CAnimationVariable 代表寬度。  
  
### <a name="remarks"></a>備註  
 您可以呼叫這個方法，以直接存取基礎 CAnimationVariable 代表寬度。  
  
##  <a name="getcy"></a>CAnimationSize::GetCY  
 提供存取權 CAnimationVariable 代表高度。  
  
```  
CAnimationVariable& GetCY();
```  
  
### <a name="return-value"></a>傳回值  
 參考封裝 CAnimationVariable 代表高度。  
  
### <a name="remarks"></a>備註  
 您可以呼叫這個方法，以直接存取基礎 CAnimationVariable 代表高度。  
  
##  <a name="getdefaultvalue"></a>CAnimationSize::GetDefaultValue  
 傳回預設值，寬度和高度。  
  
```  
CSize GetDefaultValue();
```  
  
### <a name="return-value"></a>傳回值  
 CSize 物件，其中包含預設值。  
  
### <a name="remarks"></a>備註  
 呼叫此函式可擷取先前已設定的建構函式或 SetDefaultValue 的預設值。  
  
##  <a name="getvalue"></a>CAnimationSize::GetValue  
 傳回目前的值。  
  
```  
BOOL GetValue(CSize& szValue);
```  
  
### <a name="parameters"></a>參數  
 `szValue`  
 輸出。 這個方法傳回時，包含目前的值。  
  
### <a name="return-value"></a>傳回值  
 如果為 TRUE，已順利擷取目前的值。否則為 FALSE。  
  
### <a name="remarks"></a>備註  
 呼叫此函式以擷取動畫大小的目前值。 如果此方法失敗或未初始化的寬度和大小的基礎 COM 物件，szValue 包含建構函式中或 SetDefaultValue 先前設定的預設值。  
  
##  <a name="m_cxvalue"></a>CAnimationSize::m_cxValue  
 表示動畫大小的寬度封裝的動畫變數。  
  
```  
CAnimationVariable m_cxValue;  
```  
  
##  <a name="m_cyvalue"></a>CAnimationSize::m_cyValue  
 表示動畫大小的高度封裝的動畫變數。  
  
```  
CAnimationVariable m_cyValue;  
```  
  
##  <a name="operator_csize"></a>CAnimationSize::operator CSize  
 將 CSize CAnimationSize。  
  
```  
operator CSize();
```   
  
### <a name="return-value"></a>傳回值  
 目前為 CSize 動畫大小的值。  
  
### <a name="remarks"></a>備註  
 此函式會在內部呼叫 GetValue。 如果 GetValue 因故失敗，傳回的大小將會包含預設值，寬度和高度。  
  
##  <a name="operator_eq"></a>CAnimationSize::operator =  
 指派 CAnimationSize szSrc。  
  
```  
void operator=(const CSize& szSrc);
```  
  
### <a name="parameters"></a>參數  
 `szSrc`  
 是指 CSize 或大小。  
  
### <a name="remarks"></a>備註  
 指派 CAnimationSize szSrc。 建議您這麼做之前動畫開始時，這個運算子會呼叫 SetDefaultValue，寬度和高度會重建基礎 COM 物件，如果已建立。 如果您已訂閱事件 （ValueChanged 或 IntegerValueChanged） 這個動畫物件，您需要重新啟用這些事件。  
  
##  <a name="setdefaultvalue"></a>CAnimationSize::SetDefaultValue  
 設定預設值。  
  
```  
void SetDefaultValue(const CSize& szDefault);
```  
  
### <a name="parameters"></a>參數  
 `szDefault`  
 指定新的預設大小。  
  
### <a name="remarks"></a>備註  
 使用此函式將預設值為動畫物件。 這個方法會將預設值指派給動畫大小的寬度和高度。 如果尚未建立，它也會建立基礎 COM 物件。 如果您已訂閱事件 （ValueChanged 或 IntegerValueChanged） 這個動畫物件，您需要重新啟用這些事件。  
  
## <a name="see-also"></a>另請參閱  
 [類別](../../mfc/reference/mfc-classes.md)
