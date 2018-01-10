---
title: "樹狀目錄控制項目選取 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fac551ed757cf0510f0a8b61522bc969c6b6be6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-item-selection"></a>樹狀目錄控制項目選取
當選取範圍變更從一個項目到另一個，樹狀目錄控制項 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 傳送[TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547)和[TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544)通知訊息。 兩個通知均包含一個值，該值指定變更為按一下滑鼠或是按下按鍵的結果。 通知還包含取得選取範圍的項目和遺失選取範圍的項目的相關資訊。 您可以使用這項資訊來設定項目屬性，而其屬性則視項目的選取狀態而定。 傳回**TRUE**回應**TVN_SELCHANGING**可防止選取範圍變更; 傳回**FALSE**允許變更。  
  
 應用程式可以變更選取項目，藉由呼叫[SelectItem](../mfc/reference/ctreectrl-class.md#selectitem)成員函式。  
  
## <a name="see-also"></a>另請參閱  
 [使用 CTreeCtrl](../mfc/using-ctreectrl.md)   
 [控制項](../mfc/controls-mfc.md)
