---
title: "LOGBRUSH 結構 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LOGBRUSH
dev_langs:
- C++
helpviewer_keywords:
- LOGBRUSH structure
ms.assetid: 1bf96768-52c5-4444-9bb8-d41ba2e27e68
caps.latest.revision: 11
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
ms.openlocfilehash: eea7caf6139fd43dd77163271701d170c7a744e2
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="logbrush-structure"></a>LOGBRUSH 結構
`LOGBRUSH`結構會定義樣式、 色彩和實體的筆刷的模式。 它由 Windows [CreateBrushIndirect](http://msdn.microsoft.com/library/windows/desktop/dd183487)和[ExtCreatePen](http://msdn.microsoft.com/library/windows/desktop/dd162705)函式。  
  
## <a name="syntax"></a>語法  
  
```  
typedef struct tag LOGBRUSH { /* lb */  
    UINT lbStyle;  
    COLORREF lbColor;  
    LONG lbHatch;  
} LOGBRUSH;  
```  
  
#### <a name="parameters"></a>參數  
 `lbStyle`  
 指定的筆刷樣式。 `lbStyle`成員必須為下列樣式的其中一個︰  
  
- **BS_DIBPATTERN**圖樣筆刷與裝置無關點陣圖 (DIB) 規格所定義。 如果`lbStyle`是**BS_DIBPATTERN**、 **lbHatch**成員包含壓縮 DIB 的控制代碼。  
  
- **BS_DIBPATTERNPT**圖樣筆刷與裝置無關點陣圖 (DIB) 規格所定義。 如果`lbStyle`是**BS_DIBPATTERNPT**、 **lbHatch**成員包含壓縮 DIB 的指標。  
  
- **BS_HATCHED**影線筆刷。  
  
- **BS_HOLLOW**中空筆刷。  
  
- **BS_NULL**相同**BS_HOLLOW**。  
  
- **BS_PATTERN**模式記憶體點陣圖所定義的筆刷。  
  
- **BS_SOLID**實心筆刷。  
  
 `lbColor`  
 指定的筆刷為要繪製的色彩。 如果`lbStyle`是**BS_HOLLOW**或**BS_PATTERN**樣式， **lbColor**會被忽略。 如果`lbStyle`是**BS_DIBPATTERN**或**BS_DIBPATTERNBT**，低序位文字**lbColor**指定是否**bmiColors**成員[BITMAPINFO](../../mfc/reference/bitmapinfo-structure.md)結構中包含明確的紅色、 綠色、 藍 (RGB) 值或索引目前實現邏輯調色盤。 **LbColor**成員必須是下列值之一︰  
  
- **DIB_PAL_COLORS**色彩表包含的 16 位元索引的陣列至目前實現邏輯調色盤。  
  
- **DIB_RGB_COLORS**色彩表包含常值的 RGB 值。  
  
 *lbHatch*  
 指定影線樣式。 意義取決於所定義的筆刷樣式`lbStyle`。 如果`lbStyle`是**BS_DIBPATTERN**、 **lbHatch**成員包含壓縮 DIB 的控制代碼。 如果`lbStyle`是**BS_DIBPATTERNPT**、 **lbHatch**成員包含壓縮 DIB 的指標。 如果`lbStyle`是**BS_HATCHED**、 **lbHatch**成員指定用來建立規劃的幾行的方向。 它可以是下列值之一︰  
  
- `HS_BDIAGONAL`45 度向上、 左到右規劃  
  
- `HS_CROSS`水平和垂直有斜紋  
  
- `HS_DIAGCROSS`45 度有斜紋  
  
- `HS_FDIAGONAL`45 度向下、 左到右規劃  
  
- `HS_HORIZONTAL`水平影線  
  
- `HS_VERTICAL`垂直規劃  
  
 如果`lbStyle`是**BS_PATTERN**， **lbHatch**是定義的模式，點陣圖的控制代碼。 如果`lbStyle`是**BS_SOLID**或**BS_HOLLOW**， **lbHatch**會被忽略。  
  
## <a name="remarks"></a>備註  
 雖然**lbColor**控制規劃筆刷的前景色彩[CDC::SetBkMode](../../mfc/reference/cdc-class.md#setbkmode)和[CDC::SetBkColor](../../mfc/reference/cdc-class.md#setbkcolor)函式控制項的背景色彩。  
  
## <a name="requirements"></a>需求  
 **標頭︰** wingdi.h  
  
## <a name="see-also"></a>另請參閱  
 [結構、 樣式、 回呼和訊息對應](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

