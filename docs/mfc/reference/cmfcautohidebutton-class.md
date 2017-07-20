---
title: "CMFCAutoHideButton 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::BringToTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Create
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAlignment
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetAutoHideWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetParentToolBar
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetRect
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::GetTextSize
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::HighlightButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsActive
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHighlighted
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsHorizontal
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsTop
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::IsVisible
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::Move
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDraw
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnDrawBorder
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::OnFillBackground
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ReplacePane
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowAttachedWindow
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::ShowButton
- AFXAUTOHIDEBUTTON/CMFCAutoHideButton::UnSetAutoHideMode
dev_langs:
- C++
helpviewer_keywords:
- CMFCAutoHideButton class
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
caps.latest.revision: 33
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
ms.openlocfilehash: f25072b4362b6add1682ce50fc5ee21cc065637a
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcautohidebutton-class"></a>CMFCAutoHideButton 類別
顯示或隱藏的按鈕[CDockablePane 類別](../../mfc/reference/cdockablepane-class.md)，它會設定為隱藏。  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>語法  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CMFCAutoHideButton::BringToTop](#bringtotop)||  
|[CMFCAutoHideButton::Create](#create)|建立並初始化自動隱藏按鈕。|  
|[CMFCAutoHideButton::GetAlignment](#getalignment)|擷取自動隱藏按鈕的對齊方式。|  
|[CMFCAutoHideButton::GetAutoHideWindow](#getautohidewindow)|傳回[CDockablePane](../../mfc/reference/cdockablepane-class.md) [自動隱藏] 按鈕相關聯的物件。|  
|[CMFCAutoHideButton::GetParentToolBar](#getparenttoolbar)||  
|[CMFCAutoHideButton::GetRect](#getrect)||  
|[CMFCAutoHideButton::GetSize](#getsize)|決定自動隱藏按鈕的大小。|  
|[CMFCAutoHideButton::GetTextSize](#gettextsize)|傳回自動隱藏按鈕文字標籤的大小。|  
|[CMFCAutoHideButton::HighlightButton](#highlightbutton)|反白顯示自動隱藏按鈕。|  
|[CMFCAutoHideButton::IsActive](#isactive)|指出自動隱藏按鈕是否為作用中。|  
|[CMFCAutoHideButton::IsHighlighted](#ishighlighted)|傳回自動隱藏按鈕反白顯示的狀態。|  
|[CMFCAutoHideButton::IsHorizontal](#ishorizontal)|判斷自動隱藏按鈕是水平或垂直。|  
|[CMFCAutoHideButton::IsTop](#istop)||  
|[CMFCAutoHideButton::IsVisible](#isvisible)|指出是否顯示按鈕。|  
|[CMFCAutoHideButton::Move](#move)||  
|[CMFCAutoHideButton::OnDraw](#ondraw)|當它繪製自動隱藏按鈕時，架構會呼叫這個方法。|  
|[CMFCAutoHideButton::OnDrawBorder](#ondrawborder)|當它繪製自動隱藏按鈕的邊框時，架構會呼叫這個方法。|  
|[CMFCAutoHideButton::OnFillBackground](#onfillbackground)|當它填入自動隱藏按鈕的背景時，架構會呼叫這個方法。|  
|[CMFCAutoHideButton::ReplacePane](#replacepane)||  
|[CMFCAutoHideButton::ShowAttachedWindow](#showattachedwindow)|顯示或隱藏相關聯[CDockablePane 類別](../../mfc/reference/cdockablepane-class.md)。|  
|[CMFCAutoHideButton::ShowButton](#showbutton)|顯示或隱藏自動隱藏按鈕。|  
|[CMFCAutoHideButton::UnSetAutoHideMode](#unsetautohidemode)||  
  
## <a name="remarks"></a>備註  
 在建立，`CMFCAutoHideButton`物件附加至[CDockablePane 類別](../../mfc/reference/cdockablepane-class.md)。 `CDockablePane` 物件會隨著使用者與 `CMFCAutoHideButton` 物件的互動隱藏或顯示。  
  
 根據預設，當使用者開啟自動隱藏時，架構會自動建立 `CMFCAutoHideButton`。 架構可以建立自訂 UI 類別而不是 `CMFCAutoHideButton` 類別的項目。 若要指定架構應該使用的自訂 UI 類別，請將靜態成員變數 `CMFCAutoHideBar::m_pAutoHideButtonRTS` 設定為等於自訂 UI 類別。 根據預設，此變數會設為 `CMFCAutoHideButton`。  
  
## <a name="example"></a>範例  
 下列範例示範如何建構 `CMFCAutoHideButton` 物件，以及使用 `CMFCAutoHideButton` 類別中的各種方法。 此範例示範如何初始化 `CMFCAutoHideButton` 物件 (使用其 `Create` 方法)，顯示相關聯的 `CDockablePane` 類別，並顯示自動隱藏按鈕。  
  
 [!code-cpp[NVC_MFC_RibbonApp #&32;](../../mfc/reference/codesnippet/cpp/cmfcautohidebutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMFCAutoHideButton`  
  
## <a name="requirements"></a>需求  
 **標頭：** afxautohidebutton.h  
  
##  <a name="bringtotop"></a>CMFCAutoHideButton::BringToTop  

  
```  
void BringToTop();
```  
  
### <a name="remarks"></a>備註  
  
##  <a name="create"></a>CMFCAutoHideButton::Create  
 建立並初始化自動隱藏 按鈕。  
  
```  
virtual BOOL Create(
    CMFCAutoHideBar* pParentBar,  
    CDockablePane* pAutoHideWnd,  
    DWORD dwAlignment);
```  
  
### <a name="parameters"></a>參數  
 [in] `pParentBar`  
 為父工具列指標。  
  
 [in] `pAutoHideWnd`  
 指標[CDockablePane](../../mfc/reference/cdockablepane-class.md)物件。 此自動隱藏按鈕隱藏和顯示`CDockablePane`。  
  
 [in] `dwAlignment`  
 指定按鈕的對齊與主框架視窗的值。  
  
### <a name="return-value"></a>傳回值  
 如果成功則為非零；否則為 0。  
  
### <a name="remarks"></a>備註  
 當您建立`CMFCAutoHideButton`物件時，您必須將 [自動隱藏] 按鈕關聯特定`CDockablePane`。 使用者可以使用 [自動隱藏] 按鈕隱藏和顯示相關聯`CDockablePane`。  
  
 `dwAlignment` 參數表示自動隱藏按鈕在應用程式中的位置。 這個參數可以是下列任何一個值：  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CBRS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="getalignment"></a>CMFCAutoHideButton::GetAlignment  
 擷取自動隱藏按鈕的對齊方式。  
  
```  
DWORD GetAlignment() const;  
```  
  
### <a name="return-value"></a>傳回值  
 A`DWORD`值，其中包含目前的對齊方式的自動隱藏 按鈕。  
  
### <a name="remarks"></a>備註  
 [自動隱藏] 按鈕的對齊方式會指示按鈕上的應用程式所在的位置。 它可以是下列值之一︰  
  
- `CBRS_ALIGN_LEFT`  
  
- `CBRS_ALIGN_RIGHT`  
  
- `CRBS_ALIGN_TOP`  
  
- `CBRS_ALIGN_BOTTOM`  
  
##  <a name="getautohidewindow"></a>CMFCAutoHideButton::GetAutoHideWindow  
 傳回[CDockablePane](../../mfc/reference/cdockablepane-class.md) [自動隱藏] 按鈕相關聯的物件。  
  
```  
CDockablePane* GetAutoHideWindow() const;  
```  
  
### <a name="return-value"></a>傳回值  
 相關聯的指標`CDockablePane`物件。  
  
### <a name="remarks"></a>備註  
 若要將具有 「 自動隱藏按鈕`CDockablePane`，傳遞`CDockablePane`做為參數[CMFCAutoHideButton::Create](#create)方法。  
  
##  <a name="getparenttoolbar"></a>CMFCAutoHideButton::GetParentToolBar  

  
```  
CMFCAutoHideBar* GetParentToolBar();
```  
  
### <a name="return-value"></a>傳回值  
  
### <a name="remarks"></a>備註  
  
##  <a name="getrect"></a>CMFCAutoHideButton::GetRect  

  
```  
CRect GetRect() const;  
```  
  
### <a name="return-value"></a>傳回值  
  
### <a name="remarks"></a>備註  
  
##  <a name="getsize"></a>CMFCAutoHideButton::GetSize  
 決定自動隱藏按鈕的大小。  
  
```  
CSize GetSize() const;  
```  
  
### <a name="return-value"></a>傳回值  
 A`CSize`物件，其中包含按鈕的大小。  
  
### <a name="remarks"></a>備註  
 計算的大小包含了 [自動隱藏] 按鈕的框線大小。  
  
##  <a name="gettextsize"></a>CMFCAutoHideButton::GetTextSize  
 傳回自動隱藏按鈕文字標籤的大小。  
  
```  
virtual CSize GetTextSize() const;  
```  
  
### <a name="return-value"></a>傳回值  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md)物件，其中包含的 [自動隱藏] 按鈕的文字大小。  
  
##  <a name="isactive"></a>CMFCAutoHideButton::IsActive  
 指出自動隱藏按鈕是否為作用中。  
  
```  
BOOL IsActive() const;  
```  
  
### <a name="return-value"></a>傳回值  
 `TRUE`如果 [自動隱藏] 按鈕已啟用。`FALSE`否則。  
  
### <a name="remarks"></a>備註  
 自動隱藏 按鈕時，使用中關聯[CDockablePane 類別](../../mfc/reference/cdockablepane-class.md)顯示視窗。  
  
##  <a name="ishorizontal"></a>CMFCAutoHideButton::IsHorizontal  
 判斷自動隱藏按鈕是水平或垂直。  
  
```  
BOOL IsHorizontal() const;  
```  
  
### <a name="return-value"></a>傳回值  
 如果按鈕是水平; 為非零否則為 0。  
  
### <a name="remarks"></a>備註  
 架構設定的方向[CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)您所建立的物件。  您可以使用來控制方向`dwAlignment`中的參數[CMFCAutoHideButton::Create](#create)方法。  
  
##  <a name="istop"></a>CMFCAutoHideButton::IsTop  

  
```  
BOOL IsTop() const;  
```  
  
### <a name="return-value"></a>傳回值  
  
### <a name="remarks"></a>備註  
  
##  <a name="isvisible"></a>CMFCAutoHideButton::IsVisible  
 表示 [自動隱藏] 按鈕是否可見。  
  
```  
virtual BOOL IsVisible() const;  
```  
  
### <a name="return-value"></a>傳回值  
 `TRUE`如果按鈕是可見的。`FALSE`否則。  
  
##  <a name="ondraw"></a>CMFCAutoHideButton::OnDraw  
 當它繪製自動隱藏按鈕時，架構會呼叫這個方法。  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>參數  
 [in] `pDC`  
 裝置內容的指標。  
  
### <a name="remarks"></a>備註  
 如果您想要自訂應用程式中的 自動隱藏按鈕的外觀，建立新的類別衍生自`CMFCAutoHideButton`。 在您的衍生類別中覆寫這個方法。  
  
##  <a name="ondrawborder"></a>CMFCAutoHideButton::OnDrawBorder  
 當它繪製自動隱藏按鈕的邊框時，架構會呼叫這個方法。  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rectBounds,  
    CRect rectBorderSize);
```  
  
### <a name="parameters"></a>參數  
 [in] `pDC`  
 裝置內容的指標。  
  
 [in] `rectBounds`  
 [自動隱藏] 按鈕，這個周框。  
  
 [in] `rectBorderSize`  
 為每個邊的 [自動隱藏] 按鈕的框線粗細。  
  
### <a name="remarks"></a>備註  
 如果您想要自訂您的應用程式中的每個自動隱藏 按鈕的框線，建立新的類別衍生自`CMFCAutoHideButton`。 在您的衍生類別中覆寫這個方法。  
  
##  <a name="onfillbackground"></a>CMFCAutoHideButton::OnFillBackground  
 當它填入自動隱藏按鈕的背景時，架構會呼叫這個方法。  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>參數  
 [in] `pDC`  
 裝置內容的指標。  
  
 [in] `rect`  
 [自動隱藏] 按鈕，這個周框。  
  
### <a name="remarks"></a>備註  
 如果您想要自訂您的應用程式中的 自動隱藏按鈕的背景，建立新的類別衍生自`CMFCAutoHideButton`。 在您的衍生類別中覆寫這個方法。  
  
##  <a name="showattachedwindow"></a>CMFCAutoHideButton::ShowAttachedWindow  
 顯示或隱藏相關聯[CDockablePane 類別](../../mfc/reference/cdockablepane-class.md)。  
  
```  
void ShowAttachedWindow(BOOL bShow);
```  
  
### <a name="parameters"></a>參數  
 [in] `bShow`  
 布林值，指定是否這個方法會顯示附加`CDockablePane`。  
  
##  <a name="showbutton"></a>CMFCAutoHideButton::ShowButton  
 顯示或隱藏自動隱藏按鈕。  
  
```  
virtual void ShowButton(BOOL bShow);
```  
  
### <a name="parameters"></a>參數  
 [in] `bShow`  
 布林值，指定是否要顯示 [自動隱藏] 按鈕。  
  
##  <a name="move"></a>CMFCAutoHideButton::Move  

  
```  
void Move(int nOffset);
```  
  
### <a name="parameters"></a>參數  
 [in] `nOffset`  
  
### <a name="remarks"></a>備註  
  
##  <a name="replacepane"></a>CMFCAutoHideButton::ReplacePane  

  
```  
void ReplacePane(CDockablePane* pNewBar);
```  
  
### <a name="parameters"></a>參數  
 [in] `pNewBar`  
  
### <a name="remarks"></a>備註  
  
##  <a name="unsetautohidemode"></a>CMFCAutoHideButton::UnSetAutoHideMode  
 停用自動隱藏模式。  
  
```  
virtual void UnSetAutoHideMode(CDockablePane* pFirstBarInGroup);
```  
  
### <a name="parameters"></a>參數  
 [in] `pFirstBarInGroup`  
 群組中第一個列的指標。  
  
### <a name="remarks"></a>備註  
  
##  <a name="highlightbutton"></a>CMFCAutoHideButton::HighlightButton  
 反白顯示 [自動隱藏] 按鈕。  
  
```  
virtual void HighlightButton(BOOL bHighlight);
```  
  
### <a name="parameters"></a>參數  
 `bHighlight`  
 指定新的自動隱藏 按鈕的狀態。 `TRUE`表示按鈕會反白顯示，`FALSE`表示不反白顯示的按鈕。  
  
### <a name="remarks"></a>備註  
  
##  <a name="ishighlighted"></a>CMFCAutoHideButton::IsHighlighted  
 傳回反白顯示狀態的 [自動隱藏] 按鈕。  
  
```  
virtual BOOL IsHighlighted() const;  
```  
  
### <a name="return-value"></a>傳回值  
 傳回`TRUE`自動隱藏 按鈕就會反白顯示，否則如果`FALSE`。  
  
### <a name="remarks"></a>備註  
  
## <a name="see-also"></a>另請參閱  
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [類別](../../mfc/reference/mfc-classes.md)   
 [CMFCAutoHideBar 類別](../../mfc/reference/cmfcautohidebar-class.md)   
 [CAutoHideDockSite 類別](../../mfc/reference/cautohidedocksite-class.md)
