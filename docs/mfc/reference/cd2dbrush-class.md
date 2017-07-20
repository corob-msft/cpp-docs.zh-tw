---
title: "CD2DBrush 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
dev_langs:
- C++
helpviewer_keywords:
- CD2DBrush class
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
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
ms.openlocfilehash: b9902445fb6e18df20073d132a2117c67e695b25
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cd2dbrush-class"></a>CD2DBrush 類別
ID2D1Brush 包裝函式。  
  
## <a name="syntax"></a>語法  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## <a name="members"></a>Members  
  
### <a name="protected-constructors"></a>受保護的建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[CD2DBrush::CD2DBrush](#cd2dbrush)|建構 CD2DBrush 物件。|  
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|解構函式。 D2D brush 物件終結時呼叫。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CD2DBrush::Attach](#attach)|會附加至現有的資源物件的介面|  
|[CD2DBrush::Destroy](#destroy)|終結 CD2DBrush 物件。 (覆寫[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)。)|  
|[CD2DBrush::Detach](#detach)|中斷連結物件中的資源介面|  
|[CD2DBrush::Get](#get)|傳回 ID2D1Brush 介面|  
|[CD2DBrush::GetOpacity](#getopacity)|取得這個筆刷的不透明度|  
|[CD2DBrush::GetTransform](#gettransform)|取得目前的呈現目標的轉換|  
|[CD2DBrush::IsValid](#isvalid)|檢查資源的有效性 (覆寫[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)。)|  
|[CD2DBrush::SetOpacity](#setopacity)|設定這個筆刷的不透明度|  
|[CD2DBrush::SetTransform](#settransform)|將指定的轉換套用至呈現目標，取代現有的轉換。 所有後續的繪圖作業發生在轉換後的空間|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|說明|  
|----------|-----------------|  
|[CD2DBrush::operator ID2D1Brush *](#operator_id2d1brush_star)|傳回 ID2D1Brush 介面|  
  
### <a name="protected-data-members"></a>受保護的資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|[CD2DBrush::m_pBrush](#m_pbrush)|儲存 ID2D1Brush 物件的指標。|  
|[CD2DBrush::m_pBrushProperties](#m_pbrushproperties)|筆刷屬性。|  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DBrush`  
  
## <a name="requirements"></a>需求  
 **標頭︰** afxrendertarget.h  
  
##  <a name="_dtorcd2dbrush"></a>CD2DBrush:: ~ CD2DBrush  
 解構函式。 D2D brush 物件終結時呼叫。  
  
```  
virtual ~CD2DBrush();
```  
  
##  <a name="attach"></a>CD2DBrush::Attach  
 會附加至現有的資源物件的介面  
  
```  
void Attach(ID2D1Brush* pResource);
```  
  
### <a name="parameters"></a>參數  
 `pResource`  
 現有的資源介面。 不能是 NULL  
  
##  <a name="cd2dbrush"></a>CD2DBrush::CD2DBrush  
 建構 CD2DBrush 物件。  
  
```  
CD2DBrush(
    CRenderTarget* pParentTarget,  
    CD2DBrushProperties* pBrushProperties = NULL,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>參數  
 `pParentTarget`  
 呈現目標指標。  
  
 `pBrushProperties`  
 指標的不透明度和筆刷轉換。  
  
 `bAutoDestroy`  
 指出由擁有者 (pParentTarget) 將會終結物件。  
  
##  <a name="destroy"></a>CD2DBrush::Destroy  
 終結 CD2DBrush 物件。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DBrush::Detach  
 中斷連結物件中的資源介面  
  
```  
ID2D1Brush* Detach();
```  
  
### <a name="return-value"></a>傳回值  
 中斷連結的資源介面指標。  
  
##  <a name="get"></a>CD2DBrush::Get  
 傳回 ID2D1Brush 介面  
  
```  
ID2D1Brush* Get();
```  
  
### <a name="return-value"></a>傳回值  
 如果物件尚未初始化為 NULL 的 ID2D1Brush 介面的指標。  
  
##  <a name="getopacity"></a>CD2DBrush::GetOpacity  
 取得這個筆刷的不透明度  
  
```  
FLOAT GetOpacity() const;  
```  
  
### <a name="return-value"></a>傳回值  
 介於 0 到 1，指出的筆刷不透明值。 這個值是以線性方式調整所有填滿筆刷的像素的 alpha 值的常數倍數。 在之前一起相乘範圍 0 到 1 壓制不透明度值  
  
##  <a name="gettransform"></a>CD2DBrush::GetTransform  
 取得目前的呈現目標的轉換  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;  
```  
  
### <a name="parameters"></a>參數  
 `transform`  
 這會傳回包含目前的呈現目標的轉換。 這個參數未初始化便傳遞  
  
##  <a name="isvalid"></a>CD2DBrush::IsValid  
 檢查資源的有效性  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>傳回值  
 如果資源無效，則為 TRUE否則為 FALSE。  
  
##  <a name="m_pbrush"></a>CD2DBrush::m_pBrush  
 儲存 ID2D1Brush 物件的指標。  
  
```  
ID2D1Brush* m_pBrush;  
```  
  
##  <a name="m_pbrushproperties"></a>CD2DBrush::m_pBrushProperties  
 筆刷屬性。  
  
```  
CD2DBrushProperties* m_pBrushProperties;  
```  
  
##  <a name="operator_id2d1brush_star"></a>CD2DBrush::operator ID2D1Brush *  
 傳回 ID2D1Brush 介面  
  
```  
operator ID2D1Brush*();
```   
  
### <a name="return-value"></a>傳回值  
 如果物件尚未初始化為 NULL 的 ID2D1Brush 介面的指標。  
  
##  <a name="setopacity"></a>CD2DBrush::SetOpacity  
 設定這個筆刷的不透明度  
  
```  
void SetOpacity(FLOAT opacity);
```  
  
### <a name="parameters"></a>參數  
 `opacity`  
 介於 0 到 1，指出的筆刷不透明值。 這個值是以線性方式調整所有填滿筆刷的像素的 alpha 值的常數倍數。 在之前一起相乘範圍 0 到 1 壓制不透明度值  
  
##  <a name="settransform"></a>CD2DBrush::SetTransform  
 將指定的轉換套用至呈現目標，取代現有的轉換。 所有後續的繪圖作業發生在轉換後的空間  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>參數  
 `transform`  
 要套用至呈現目標轉換  
  
## <a name="see-also"></a>另請參閱  
 [類別](../../mfc/reference/mfc-classes.md)
