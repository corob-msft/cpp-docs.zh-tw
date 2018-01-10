---
title: "通知來自 Rich Edit 控制項 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- messages [MFC], notification [MFC]
- CRichEditCtrl class [MFC], notifications
- rich edit controls [MFC], notifications
- notifications [MFC], from CRichEditCtrl
ms.assetid: eb5304fe-f4f3-4557-9ebf-3095dea383c4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcfcb2e4fe333db1ed629489b405255d4ab050b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="notifications-from-a-rich-edit-control"></a>來自 Rich Edit 控制項的告知
通知訊息報告事件影響 rich edit 控制項 ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))。 它們可以處理由父視窗，或使用訊息反映由 rich edit 控制項本身。 Rich edit 控制項支援的所有編輯控制項以及數個其他項目搭配使用的通知訊息。 您可以判斷哪些通知訊息 rich edit 控制項傳送其父視窗藉由設定它的 「 事件遮罩 」。  
  
 若要設定事件遮罩的 rich edit 控制項，使用[SetEventMask](../mfc/reference/cricheditctrl-class.md#seteventmask)成員函式。 您可以擷取目前事件遮罩的 rich edit 控制項使用[GetEventMask](../mfc/reference/cricheditctrl-class.md#geteventmask)成員函式。  
  
 下面列出數個特定通知，以及它們的用法：  
  
-   **EN_MSGFILTER**處理**EN_MSGFILTER**通知可讓類別、 任一個的豐富編輯控制項或其父視窗、 篩選所有鍵盤和滑鼠輸入至控制項。 此處理常式可以防止鍵盤或滑鼠訊息處理，或可以藉由修改指定變更訊息[MSGFILTER](http://msdn.microsoft.com/library/windows/desktop/bb787936)結構。  
  
-   **EN_PROTECTED**處理**EN_PROTECTED**通知訊息來偵測當使用者嘗試修改受保護的文字。 若要將文字範圍標示為受保護，您可以設定受保護的字元效果。 如需詳細資訊，請參閱[Rich Edit 控制項中的字元格式](../mfc/character-formatting-in-rich-edit-controls.md)。  
  
-   **EN_DROPFILES**您可以讓使用者將卸除 rich edit 控制項中的檔案處理**EN_DROPFILES**通知訊息。 指定[ENDROPFILES](http://msdn.microsoft.com/library/windows/desktop/bb787895)結構包含要卸除之檔案的相關資訊。  
  
-   **EN_SELCHANGE**應用程式可以偵測到目前的選取範圍變更處理**EN_SELCHANGE**通知訊息。 指定通知訊息[SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/bb787952)結構，其中包含新的選取範圍的相關資訊。  
  
## <a name="see-also"></a>請參閱  
 [使用 CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [控制項](../mfc/controls-mfc.md)
