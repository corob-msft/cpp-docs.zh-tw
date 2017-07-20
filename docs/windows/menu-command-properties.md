---
title: "Menu Command Properties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "menu items, properties"
ms.assetid: 6d308205-3c9e-42f2-ab42-45e656940e45
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Menu Command Properties
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

下列資訊的組織方式是根據您選取功能表命令時出現在[屬性視窗](../Topic/Properties%20Window.md)的 \[功能表\] 屬性。 雖然 \[屬性\] 視窗也可讓您依類別檢視這些屬性，但這些是依字母順序列出  
  
|屬性|描述|  
|--------|--------|  
|**Break**|可以是下列值之一：<br /><br /> -   **無** \(預設值\)：不換行<br />-   **資料行**：對於靜態功能表，這個值會將功能表命令放在新行上。 對於快顯功能表，這個值會將功能表命令放在資料行中，而且資料行之間沒有分隔線。 設定這個屬性只會在執行階段影響功能表的外觀，但在功能表編輯器中卻不會。<br />-   **列**：與資料行相同，除了針對快顯功能表，此值會以垂直線區隔新的資料行與舊的資料行。 設定這個屬性只會在執行階段影響功能表的外觀，但在功能表編輯器中卻不會。|  
|**標題**|標示功能表命令的文字 \(功能表名稱\)。 若要讓功能表命令的其中一個大寫字母成為助憶鍵，請在其前面加下連字號 \(&\)。|  
|**已核取**|若為 True，一開始就會核取功能表命令。 類型：Bool。 預設值：False。|  
|**已啟用**|若為 **False**，則會停用功能表項目。|  
|**呈現灰色**|若為 True，功能表命令一開始就會呈現灰色，而且沒有作用。 類型：Bool。 預設值：False。|  
|**說明**|將功能表項目對齊右邊。 例如，\[**說明**\] 功能表命令一律在所有 Windows 應用程式的右邊。 如果您在功能表項目上設定這個屬性，該項目將出現在功能表的最右邊和最尾端。 適用於最上層項目。 預設值：**False**。|  
|**ID**|定義在標頭中的符號。 類型：符號、整數或引號字串。 您可以使用任何通常可在任何編輯器使用的符號，即使[屬性視窗](../Topic/Properties%20Window.md)未提供可讓您從中選取的下拉式清單也一樣。|  
|**快顯**|若為 True，功能表命令即是快顯功能表。 類型：Bool。 預設值：True，表示功能表列上的最上層功能表；否則為 False。|  
|**提示**|包含反白顯示此功能表命令時要出現在狀態列的文字。 文字會放在字串表中，其識別碼與功能表命令相同。 這個屬性適用於任何類型的專案，但執行階段功能則專屬於 MFC。|  
|**由右至左對齊**|在執行階段將功能表列上的功能表命令靠右對齊。 類型：Bool。 預設值：False。|  
|**順序由右至左**|當介面當地語系化為任何由右至左讀取的語言 \(例如希伯來文或阿拉伯文\) 時，可讓功能表命令由右至左顯示。|  
|**Separator**|若為 True，功能表命令為分隔符號。 類型：Bool。 預設值：False。|  
  
 如需將資源加入 Managed 專案的相關資訊，請參閱《.NET Framework 開發人員手冊》中的[應用程式中的資源](../Topic/Resources%20in%20Desktop%20Apps.md)。如需手動將資源檔加入 Managed 專案、存取資源、顯示靜態資源及指派資源字串給屬性的相關資訊，請參閱[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)。  
  
## 需求  
 Win32  
  
## 請參閱  
 [Menu Editor](../mfc/menu-editor.md)