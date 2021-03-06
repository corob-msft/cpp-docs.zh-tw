---
title: CD2DBrush 類別
ms.date: 11/04/2016
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
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
ms.openlocfilehash: 9e0be4b3b4f39d8fcf32f713bc8765d1f344babe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517880"
---
# <a name="cd2dbrush-class"></a>CD2DBrush 類別

ID2D1Brush 包裝函式。

## <a name="syntax"></a>語法

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>成員

### <a name="protected-constructors"></a>受保護的建構函式

|名稱|描述|
|----------|-----------------|
|[CD2DBrush::CD2DBrush](#cd2dbrush)|建構 CD2DBrush 物件。|
|[CD2DBrush:: ~ CD2DBrush](#_dtorcd2dbrush)|解構函式。 D2D 筆刷物件正在被終結時呼叫。|

### <a name="public-methods"></a>公用方法

|名稱|描述|
|----------|-----------------|
|[CD2DBrush::Attach](#attach)|將現有的資源物件的介面|
|[CD2DBrush::Destroy](#destroy)|終結 CD2DBrush 物件。 (覆寫[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy)。)|
|[CD2DBrush::Detach](#detach)|中斷連結物件中的資源介面|
|[CD2DBrush::Get](#get)|傳回 ID2D1Brush 介面|
|[CD2DBrush::GetOpacity](#getopacity)|取得這個筆刷的不透明度|
|[CD2DBrush::GetTransform](#gettransform)|取得目前的轉譯目標的轉換|
|[CD2DBrush::IsValid](#isvalid)|檢查資源的有效性 (會覆寫[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid)。)|
|[CD2DBrush::SetOpacity](#setopacity)|設定這個筆刷的不透明度|
|[CD2DBrush::SetTransform](#settransform)|指定的轉換套用到轉譯目標中，取代現有的轉換。 所有後續的繪圖作業發生在轉換後的空間|

### <a name="public-operators"></a>公用運算子

|名稱|描述|
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

**標頭：** afxrendertarget.h

##  <a name="_dtorcd2dbrush"></a>  CD2DBrush:: ~ CD2DBrush

解構函式。 D2D 筆刷物件正在被終結時呼叫。

```
virtual ~CD2DBrush();
```

##  <a name="attach"></a>  CD2DBrush::Attach

將現有的資源物件的介面。

```
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>參數

*pResource*<br/>
現有的資源介面。 不可以是 NULL。

##  <a name="cd2dbrush"></a>  CD2DBrush::CD2DBrush

建構 CD2DBrush 物件。

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>參數

*pParentTarget*<br/>
到轉譯目標的指標。

*pBrushProperties*<br/>
不透明度和筆刷轉換指標。

*bAutoDestroy*<br/>
表示擁有者 (pParentTarget) 將會終結物件。

##  <a name="destroy"></a>  CD2DBrush::Destroy

終結 CD2DBrush 物件。

```
virtual void Destroy();
```

##  <a name="detach"></a>  CD2DBrush::Detach

中斷連結物件中的資源介面。

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>傳回值

中斷連結的資源介面指標。

##  <a name="get"></a>  CD2DBrush::Get

傳回 ID2D1Brush 介面

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>傳回值

如果物件尚未初始化為 NULL 的 ID2D1Brush 介面的指標。

##  <a name="getopacity"></a>  CD2DBrush::GetOpacity

取得這個筆刷的不透明度

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>傳回值

介於 0 到 1，指出筆刷的不透明度值。 這個值是以線性方式調整所有填滿筆刷的像素的 alpha 值的常數倍數。 不透明度值會限制在 0 到 1 的範圍之前一起相乘。

##  <a name="gettransform"></a>  CD2DBrush::GetTransform

取得目前的轉譯目標的轉換

```
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>參數

*transform*<br/>
這會傳回包含目前的轉譯目標的轉換。 這個參數會以未初始化的狀態傳遞。

##  <a name="isvalid"></a>  CD2DBrush::IsValid

檢查資源的有效性

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>傳回值

如果資源無效，則為 TRUE否則為 FALSE。

##  <a name="m_pbrush"></a>  CD2DBrush::m_pBrush

儲存 ID2D1Brush 物件的指標。

```
ID2D1Brush* m_pBrush;
```

##  <a name="m_pbrushproperties"></a>  CD2DBrush::m_pBrushProperties

筆刷屬性。

```
CD2DBrushProperties* m_pBrushProperties;
```

##  <a name="operator_id2d1brush_star"></a>  CD2DBrush::operator ID2D1Brush *

傳回 ID2D1Brush 介面

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>傳回值

如果物件尚未初始化為 NULL 的 ID2D1Brush 介面的指標。

##  <a name="setopacity"></a>  CD2DBrush::SetOpacity

設定這個筆刷的不透明度

```
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>參數

*不透明度*<br/>
介於 0 到 1，指出筆刷的不透明度值。 這個值是以線性方式調整所有填滿筆刷的像素的 alpha 值的常數倍數。 不透明度值會限制在 0 到 1 的範圍之前一起相乘。

##  <a name="settransform"></a>  CD2DBrush::SetTransform

指定的轉換套用到轉譯目標中，取代現有的轉換。 所有後續的繪圖作業會在轉換後的空間發生。

```
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>參數

*transform*<br/>
要套用到轉譯目標的轉換

## <a name="see-also"></a>另請參閱

[類別](../../mfc/reference/mfc-classes.md)
