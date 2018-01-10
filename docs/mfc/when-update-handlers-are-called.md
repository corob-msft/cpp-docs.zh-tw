---
title: "呼叫更新處理常式的時機 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- updating user interface objects [MFC]
- command routing [MFC], update commands
- toolbar buttons [MFC], enabling
- disabling toolbar buttons
- menus [MFC], initializing
- update handlers [MFC]
- disabling menu items
- toolbars [MFC], updating
- menus [MFC], updating as context changes
- toolbar controls [MFC], updated during OnIdle method [MFC]
- menu items, enabling
- command routing [MFC], update handlers
- update handlers, calling
ms.assetid: 7359f6b1-4669-477d-bd99-690affed08d9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaf2773a2d9e393c783a39e01c75f8efa62796df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="when-update-handlers-are-called"></a>呼叫更新處理常式的時機
假設使用者在 [檔案] 功能表上按一下滑鼠，即產生 `WM_INITMENUPOPUP` 訊息。 架構的更新機制會統一更新 [檔案] 功能表上的所有項目，之後使用者才能看到功能表下拉式清單。  
  
 為了如此做，架構會沿著標準命令路由的路徑，路由快顯功能表中所有功能表項目的更新命令。 要路由的命令目標有機會更新所有功能表項目，其方式是透過比對更新命令與適當的訊息對應項目 (格式為 `ON_UPDATE_COMMAND_UI`) 以及呼叫「更新處理常式」函式。 因此，對於有六個功能表項目的功能表，會送出六個更新命令。如果對於功能表項目的命令 ID 存在更新處理常式，則會該呼叫處理常式進行更新。 否則，架構會檢查是否存在該命令 ID 的處理常式，並適當地啟用或停用功能表項目。  
  
 如果在命令路由期間，架構沒有找到 `ON_UPDATE_COMMAND_UI` 項目，它會自動啟用使用者介面物件 (若有具相同命令 ID 的 `ON_COMMAND` 項目)。 否則，它會停用使用者介面物件。 因此，為確保啟用使用者介面物件，請提供物件產生之命令的處理常式，或為其提供更新處理常式。 請參閱主題中的圖[使用者介面物件和命令 Id](../mfc/user-interface-objects-and-command-ids.md)。  
  
 可以停用使用者介面物件的預設停用。 如需詳細資訊，請參閱[m_bAutoMenuEnable](../mfc/reference/cframewnd-class.md#m_bautomenuenable)類別成員`CFrameWnd`中*MFC 參考*。  
  
 功能表初始化在架構中為自動執行，當應用程式收到 `WM_INITMENUPOPUP` 訊息時便會發生。 在閒置迴圈期間，架構會搜尋按鈕更新處理常式的命令路由，方式就和搜尋功能表幾乎一樣。  
  
## <a name="see-also"></a>請參閱  
 [如何：更新使用者介面物件](../mfc/how-to-update-user-interface-objects.md)
