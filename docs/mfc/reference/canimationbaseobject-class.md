---
title: "CAnimationBaseObject 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationBaseObject class
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c714c78b7017ed314b30f64df4bfceb587226c15
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject 類別
所有動畫物件的基底類別。  
  
## <a name="syntax"></a>語法  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|多載。 建構的動畫物件。|  
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|解構函式。 動畫在物件終結時呼叫。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|加入分鏡腳本與封裝的動畫變數的轉換。|  
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|移除所有相關的轉換。|  
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|判斷動畫物件是否包含特定的動畫變數。|  
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|建立轉換與動畫物件相關聯。|  
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|卸離父動畫控制器中的動畫物件。|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|設定變更的整數值的事件處理常式。|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|設定值變更事件處理常式。|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|會告知相關的轉換是否會自動終結。|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|傳回目前的群組識別碼。|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|傳回目前的物件識別碼。|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|傳回使用者定義的資料。|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|設定自動終結轉換訂單的旗標。|  
|[CAnimationBaseObject::SetID](#setid)|設定新的識別碼。|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|設定使用者定義的資料。|  
  
### <a name="protected-methods"></a>受保護的方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|會收集包含的動畫變數的指標。|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|建立動畫物件和其容器中所包含的動畫變數之間的關聯性。|  
  
### <a name="protected-data-members"></a>受保護的資料成員  
  
|名稱|說明|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|指定是否應該自動終結相關的轉換。|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|儲存使用者定義的資料。|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|指定的動畫物件的群組識別碼。|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|指定的動畫物件的物件識別碼。|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|父動畫控制器指標。|  
  
## <a name="remarks"></a>備註  
 這個類別會實作所有動畫物件的基本方法。 動畫物件可以代表值、 點、 大小、 矩形或在應用程式，以及任何自訂的項目中的色彩。 動畫物件會儲存在動畫群組 （請參閱 CAnimationGroup）。 每個群組可以個別建立動畫，而且可以被視為腳本的類比。 動畫物件會封裝一或多個動畫變數 （請參閱 CAnimationVariable），根據邏輯表示法。 例如，CAnimationRect 包含四個動畫變數為每個矩形的邊的一個變數。 每個動畫物件的類別會公開多載還得方法，應該用來將轉換套用至封裝的動畫變數。 動畫物件即可識別的物件識別碼 （選擇性） 和群組識別碼。 群組識別碼需要加上動畫物件至正確的群組，但是如果未指定群組識別碼，物件會在識別碼為 0 的預設群組中。 如果您呼叫具有不同的 GroupID SetID，動畫物件將會移到另一個群組 （必要時，會建立新的群組）。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>需求  
 **標頭：** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationbaseobject"></a>CAnimationBaseObject:: ~ CAnimationBaseObject  
 解構函式。 動畫在物件終結時呼叫。  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="applytransitions"></a>CAnimationBaseObject::ApplyTransitions  
 加入分鏡腳本與封裝的動畫變數的轉換。  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>參數  
 `pStoryboard`  
 分鏡腳本指標。  
  
 `bDependOnKeyframes`  
 包含這個方法會將那些不相依於主要畫面格的轉換。  
  
### <a name="return-value"></a>傳回值  
 如果已成功加入轉換，則為 TRUE。  
  
### <a name="remarks"></a>備註  
 新增相關的轉換，已加入至分鏡腳本的 （在衍生類別中的多載方法），還得使用。  
  
##  <a name="canimationbaseobject"></a>CAnimationBaseObject::CAnimationBaseObject  
 建構的動畫物件。  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>參數  
 `nGroupID`  
 指定群組識別碼。  
  
 `nObjectID`  
 指定物件識別碼。  
  
 `dwUserData`  
 使用者定義資料，可以稍後在執行階段擷取並與動畫物件相關聯。  
  
### <a name="remarks"></a>備註  
 建構動畫物件，並指派預設物件識別碼 (0) 和群組識別碼 (0)。  
  
##  <a name="cleartransitions"></a>CAnimationBaseObject::ClearTransitions  
 移除所有相關的轉換。  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>參數  
 `bAutodestroy`  
 指定是否要自動終結轉換物件，或只會移除從相關的清單。  
  
### <a name="remarks"></a>備註  
 移除所有相關的轉換，如果為 TRUE，否則 bAutodestroy 或 m_bAutodestroyTransitions 旗標會終結。 轉換不會在堆疊上配置時，才應該會自動終結。 如果上述的旗標為 FALSE，轉換會只會移除從內部清單中相關的轉換。  
  
##  <a name="containsvariable"></a>CAnimationBaseObject::ContainsVariable  
 判斷動畫物件是否包含特定的動畫變數。  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>參數  
 `pVariable`  
 動畫變數的指標。  
  
### <a name="return-value"></a>傳回值  
 動畫變數是否包含在動畫物件; 如果為 TRUE否則為 FALSE。  
  
### <a name="remarks"></a>備註  
 這個方法可以用來判斷動畫物件中是否包含指定 pVariable 動畫變數。 動畫物件，根據其類型，可能包含數個動畫變數。 例如，CAnimationColor 包含三個變數，一個用於每個色彩元件 （紅色、 綠色和藍色）。 當動畫變數的值變更時，會傳送 Windows 動畫 API ValueChanged 或 IntegerValueChanged 事件 （如果啟用），以及此事件的參數是介面 IUIAnimationVariable 動畫變數的指標。 此方法可協助從包含 COM 物件的指標取得動畫的指標。  
  
##  <a name="createtransitions"></a>CAnimationBaseObject::CreateTransitions  
 建立轉換與動畫物件相關聯。  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>傳回值  
 如果已成功; 建立轉換，則為 TRUE。否則為 FALSE。  
  
### <a name="remarks"></a>備註  
 循環查看封裝在衍生的動畫物件的動畫變數的清單，並建立每個動畫變數相關聯的轉換。  
  
##  <a name="detachfromcontroller"></a>CAnimationBaseObject::DetachFromController  
 卸離父動畫控制器中的動畫物件。  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>備註  
 這個方法是在內部使用。  
  
##  <a name="enableintegervaluechangedevent"></a>CAnimationBaseObject::EnableIntegerValueChangedEvent  
 設定變更的整數值的事件處理常式。  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>參數  
 `pController`  
 父控制器指標。  
  
 `bEnable`  
 指定是否要啟用或停用整數值變更事件。  
  
### <a name="remarks"></a>備註  
 如果已啟用的整數值變更事件處理常式，您可以處理此事件在 CAnimationController::OnAnimationIntegerValueChanged 方法，應該 CAnimationController 衍生類別中覆寫。 每次動畫的整數值已變更，都會呼叫這個方法。  
  
##  <a name="enablevaluechangedevent"></a>CAnimationBaseObject::EnableValueChangedEvent  
 設定值變更事件處理常式。  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>參數  
 `pController`  
 父控制器指標。  
  
 `bEnable`  
 指定是否要啟用或停用的值變更事件。  
  
### <a name="remarks"></a>備註  
 如果已啟用的值變更事件處理常式，您可以處理此事件在 CAnimationController::OnAnimationValueChanged 方法，應該 CAnimationController 衍生類別中覆寫。 每次動畫值已變更，都會呼叫這個方法。  
  
##  <a name="getanimationvariablelist"></a>CAnimationBaseObject::GetAnimationVariableList  
 會收集包含的動畫變數的指標。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>參數  
 `lst`  
 必須填入動畫物件中包含的動畫變數的清單。  
  
### <a name="remarks"></a>備註  
 這是必須在衍生類別中覆寫的純虛擬方法。 動畫物件，根據其類型，包含一或多個動畫變數。 例如，CAnimationPoint 包含兩個變數，X 和 Y 座標分別表示。 CAnimationBaseObject 的基底類別會實作某些泛型方法，執行動畫變數的清單︰ ApplyTransitions、 ClearTransitions、 EnableValueChangedEvent、 EnableIntegerValueChangedEvent。 這些方法會呼叫 GetAnimationVariableList，其中會填入在衍生類別中特定動畫物件中包含的實際動畫變數，然後循環清單並執行必要的動作。 如果您建立自訂動畫物件時，您必須將加入 lst 該物件中包含的所有動畫變數。  
  
##  <a name="getautodestroytransitions"></a>CAnimationBaseObject::GetAutodestroyTransitions  
 會告知相關的轉換是否會自動終結。  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>傳回值  
 如果為 TRUE，會自動; 終結相關的轉換如果為 FALSE，藉由呼叫應用程式應該被解除配置轉換的物件。  
  
### <a name="remarks"></a>備註  
 依預設此旗標為 TRUE。 只有當您配置在堆疊上的轉換和/或轉換應該被呼叫的應用程式解除配置，請設定此旗標。  
  
##  <a name="getgroupid"></a>CAnimationBaseObject::GetGroupID  
 傳回目前的群組識別碼。  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>傳回值  
 目前的群組識別碼。  
  
### <a name="remarks"></a>備註  
 使用此方法來擷取群組識別碼。 如果群組識別碼尚未設定明確建構函式中或 SetID，的 0。  
  
##  <a name="getobjectid"></a>CAnimationBaseObject::GetObjectID  
 傳回目前的物件識別碼。  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>傳回值  
 目前的物件識別碼。  
  
### <a name="remarks"></a>備註  
 使用此方法來擷取物件識別碼。 如果物件識別碼尚未設定明確建構函式中或 SetID，的 0。  
  
##  <a name="getuserdata"></a>CAnimationBaseObject::GetUserData  
 傳回使用者定義的資料。  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>傳回值  
 自訂資料的值。  
  
### <a name="remarks"></a>備註  
 呼叫這個方法來擷取在執行階段自訂的資料。 傳回的值將會是 0，如果它未明確初始化建構函式中或 SetUserData。  
  
##  <a name="m_bautodestroytransitions"></a>CAnimationBaseObject::m_bAutodestroyTransitions  
 指定是否應該自動終結相關的轉換。  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="m_dwuserdata"></a>CAnimationBaseObject::m_dwUserData  
 儲存使用者定義的資料。  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="m_ngroupid"></a>CAnimationBaseObject::m_nGroupID  
 指定的動畫物件的群組識別碼。  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_nobjectid"></a>CAnimationBaseObject::m_nObjectID  
 指定的動畫物件的物件識別碼。  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="m_pparentcontroller"></a>CAnimationBaseObject::m_pParentController  
 父動畫控制器指標。  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="setautodestroytransitions"></a>CAnimationBaseObject::SetAutodestroyTransitions  
 設定自動終結轉換訂單的旗標。  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>參數  
 `bValue`  
 指定自動終結旗標。  
  
### <a name="remarks"></a>備註  
 只有當您配置轉換的物件，使用新的運算子，請設定此旗標。 如果基於某些原因會在堆疊配置轉換物件，自動終結旗標應該是 FALSE。 依預設此旗標為 TRUE。  
  
##  <a name="setid"></a>CAnimationBaseObject::SetID  
 設定新的識別碼。  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>參數  
 `nObjectID`  
 指定新的物件識別碼。  
  
 `nGroupID`  
 指定新的群組識別碼。  
  
### <a name="remarks"></a>備註  
 讓使用者能夠變更物件識別碼和群組識別碼。 如果新的群組識別碼不同於目前的識別碼，動畫物件移到另一個群組 （新的群組將會建立，如有必要）。  
  
##  <a name="setparentanimationobjects"></a>CAnimationBaseObject::SetParentAnimationObjects  
 建立動畫物件和其容器中所包含的動畫變數之間的關聯性。  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>備註  
 這是可以用來建立動畫物件和其容器中所包含的動畫變數之間的關聯性的協助程式。 它會循環查看動畫變數，並設定父動畫物件，以每個動畫變數的返回指標。 在目前的實作中 CAnimationBaseObject::ApplyTransitions 建立實際的關聯性，因此反向指標才會進行設定呼叫 CAnimationGroup::Animate。 了解關聯性可能很有幫助您處理事件及要取得父動畫物件從 CAnimationVariable （使用 CAnimationVariable::GetParentAnimationObject） 時。  
  
##  <a name="setuserdata"></a>CAnimationBaseObject::SetUserData  
 設定使用者定義的資料。  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>參數  
 `dwUserData`  
 指定自訂的資料。  
  
### <a name="remarks"></a>備註  
 使用此方法將自訂資料與動畫物件。 這項資料可能會稍後在執行階段由擷取 GetUserData。  
  
## <a name="see-also"></a>另請參閱  
 [類別](../../mfc/reference/mfc-classes.md)
