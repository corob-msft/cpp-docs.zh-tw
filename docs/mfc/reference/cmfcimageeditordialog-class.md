---
title: "CMFCImageEditorDialog 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog
- AFXIMAGEEDITORDIALOG/CMFCImageEditorDialog::CMFCImageEditorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCImageEditorDialog class
ms.assetid: 6a7d08f3-1ec2-4062-9b79-a0c2776b58d1
caps.latest.revision: 24
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
ms.openlocfilehash: 1a629f9699aa2d6fb185737b51b36259ce574fe0
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcimageeditordialog-class"></a>CMFCImageEditorDialog 類別
`CMFCImageEditorDialog`類別支援影像編輯器對話方塊。  
  
## <a name="syntax"></a>語法  
  
```  
class CMFCImageEditorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CMFCImageEditorDialog::CMFCImageEditorDialog](#cmfcimageeditordialog)|建構 `CMFCImageEditorDialog` 物件。|  
  
## <a name="remarks"></a>備註  
 `CMFCImageEditorDialog`類別提供一個對話方塊，其中包含︰  
  
-   您用來修改映像中的個別像素圖片區域。  
  
-   繪圖工具來修改圖片的區域中的像素。  
  
-   若要指定使用繪圖工具的色彩調色盤的色彩。  
  
-   預覽區域會顯示您的編輯的效果。  
  
 下圖顯示影像編輯器 對話方塊。  
  
 ![CMFCImageEditorDialog 對話方塊](../../mfc/reference/media/imageedit.png "imageedit")  
  
 其中一種方式使用`CMFCImageEditorDialog`物件是將它傳遞`CBitmap`編輯映像。 請勿建立大型影像，因為映像編輯區域具有大小限制，而且邏輯像素大小會調整，以納入區域。 呼叫`DoModal`方法，以啟動強制回應對話方塊。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCImageEditorDialog](../../mfc/reference/cmfcimageeditordialog-class.md)  
  
## <a name="requirements"></a>需求  
 **標頭︰** afximageeditordialog.h  
  
##  <a name="cmfcimageeditordialog"></a>CMFCImageEditorDialog::CMFCImageEditorDialog  
 建構 `CMFCImageEditorDialog` 物件。  
  
```  
CMFCImageEditorDialog(
    CBitmap* pBitmap,  
    CWnd* pParent=NULL,  
    int nBitsPixel=-1);
```  
  
### <a name="parameters"></a>參數  
 `pBitmap`  
 映像的指標。  
  
 `pParent`  
 目前的影像編輯器對話方塊的父視窗的指標。  
  
 `nBitsPixel`  
 用來表示的色彩也稱為色彩深度的單一像素的位元數。  如果`nBitsPixel`參數為-1，色彩深度衍生自所指定的影像`pBitmap`參數。 預設值為 -1。  
  
### <a name="return-value"></a>傳回值  
 若要修改影像，影像將指標傳遞至`CMFCImageEditorDialog`建構函式。 然後呼叫`DoModal`方法來開啟強制回應對話方塊。 當`DoModal`方法傳回時，點陣圖會包含新的映像。  
  
### <a name="remarks"></a>備註  
  
### <a name="example"></a>範例  
 下列範例示範如何建構的物件`CMFCImageEditorDialog`類別。 這個範例是屬於[新的控制項範例](../../visual-cpp-samples.md)。  
  
 [!code-cpp[NVC_MFC_NewControls #&8;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_1.cpp)]  
[!code-cpp[NVC_MFC_NewControls #&40;](../../mfc/reference/codesnippet/cpp/cmfcimageeditordialog-class_2.cpp)]  
  
## <a name="see-also"></a>另請參閱  
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [類別](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar 類別](../../mfc/reference/cmfctoolbar-class.md)
