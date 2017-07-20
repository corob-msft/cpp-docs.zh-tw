---
title: "CMFCImageEditorPaletteBar 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::GetRowHeight
- AFXIMAGEEDITORDIALOG/CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorPaletteBar class
ms.assetid: 3fb7ba8e-f254-4d56-b913-9941b4ed8138
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f6b987a27b43d713835a71dd5c31587020f23f2f
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditorpalettebar-class"></a>CMFCImageEditorPaletteBar 類別
提供影像編輯器對話方塊調色盤列功能。  
  
## <a name="syntax"></a>語法  
  
```  
class CMFCImageEditorPaletteBar : public CMFCToolBar  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>公用方法  
  
|||  
|-|-|  
|名稱|說明|  
|[CMFCImageEditorPaletteBar::GetRowHeight](#getrowheight)|傳回工具列按鈕的高度。 (覆寫[CMFCToolBar::GetRowHeight](../../mfc/reference/cmfctoolbar-class.md#getrowheight)。)|  
|[CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable](#isbuttonextrasizeavailable)|決定工具列是否會顯示擴充框線的按鈕。 (覆寫[CMFCToolBar::IsButtonExtraSizeAvailable](../../mfc/reference/cmfctoolbar-class.md#isbuttonextrasizeavailable)。)|  
  
### <a name="remarks"></a>備註  
 這個類別不是直接從您的程式碼使用。  
  
 架構會使用這個類別來顯示調色盤列在 影像編輯器對話方塊。 如需 [影像編輯器] 對話方塊的詳細資訊，請參閱[CMFCImageEditorDialog 類別](../../mfc/reference/cmfcimageeditordialog-class.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CMFCBaseToolBa](../../mfc/reference/cmfcbasetoolbar-class.md)  
  
 [CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)  
  
 [CMFCImageEditorPaletteBar](../../mfc/reference/cmfcimageeditorpalettebar-class.md)  
  
## <a name="requirements"></a>需求  
 **標頭︰** afximageeditordialog.h  
  
##  <a name="getrowheight"></a>CMFCImageEditorPaletteBar::GetRowHeight  
 傳回工具列按鈕的高度。  
  
```  
virtual int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>傳回值  
 在工具列上的每個按鈕的高度。  
  
##  <a name="isbuttonextrasizeavailable"></a>CMFCImageEditorPaletteBar::IsButtonExtraSizeAvailable  
 決定工具列是否會顯示擴充框線的按鈕。  
  
```  
virtual BOOL IsButtonExtraSizeAvailable() const;  
```  
  
### <a name="return-value"></a>傳回值  
 此方法會傳回 `FALSE`。  
  
## <a name="see-also"></a>另請參閱  
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [類別](../../mfc/reference/mfc-classes.md)   
 [CMFCImageEditorDialog 類別](../../mfc/reference/cmfcimageeditordialog-class.md)
