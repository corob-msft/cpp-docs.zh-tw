---
title: "加入類別對話方塊 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.addclass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "加入類別對話方塊"
ms.assetid: 916259b8-8e5f-4267-bd10-313483beba67
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# 加入類別對話方塊
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

\[加入類別\] 對話方塊包含的範本可讓您：  
  
-   開啟對應的程式碼精靈，如果有的話。 如需詳細資訊，請參閱[使用 &#91;程式碼精靈&#93; 加入功能](../ide/adding-functionality-with-code-wizards-cpp.md)。  
  
 \-或\-  
  
-   在專案中加入適當的檔案和原始程式碼，自動建立新類別。  
  
 您可以從 \[專案\] 功能表、**方案總管**或 \[類別檢視\][](http://msdn.microsoft.com/zh-tw/8d7430a9-3e33-454c-a9e1-a85e3d2db925)，存取 \[加入類別\] 對話方塊。  
  
> [!NOTE]
>  當您嘗試加入不適合目前專案的類別時，您會收到錯誤訊息。 按一下 \[確定\] 返回 \[加入類別\] 對話方塊。  
  
## 加入類別範本  
 \[加入類別\] 範本有四個類別：.NET、ATL、MFC 和泛型。 當您在 \[範本\] 窗格中選取範本時，描述選項的文字會出現在 \[類別\] 和 \[範本\] 窗格下。  
  
### .NET  
  
|範本|精靈|  
|--------|--------|  
|ASP.NET Web 服務|無法使用|  
|元件類別 \(.NET\)|無法使用|  
|安裝程式類別 \(.NET\)|無法使用|  
|使用者控制項 \(.NET\)|無法使用|  
|Windows Form \(.NET\)|無法使用|  
  
### ATL  
  
|範本|精靈|  
|--------|--------|  
|將 ATL 支援加入 MFC|無法使用|  
|ATL Active Server Page 元件|[ATL Active Server Page 元件精靈](../atl/reference/atl-active-server-page-component-wizard.md)|  
|ATL 控制項|[ATL 控制項精靈](../atl/reference/atl-control-wizard.md)|  
|ATL 對話方塊|[ATL 對話方塊精靈](../atl/reference/atl-dialog-wizard.md)|  
|ATL COM\+ 1.0 元件|[ATL COM\+ 1.0 元件精靈](../atl/reference/atl-com-plus-1-0-component-wizard.md)|  
|ATL OLEDB 消費者|[ATL OLE DB 消費者精靈](../atl/reference/atl-ole-db-consumer-wizard.md)|  
|ATL OLEDB 提供者|[ATL OLE DB 提供者精靈](../atl/reference/atl-ole-db-provider-wizard.md)|  
|ATL 屬性頁|[ATL 屬性頁精靈](../atl/reference/atl-property-page-wizard.md)|  
|ATL 簡單物件|[ATL 簡單物件精靈](../atl/reference/atl-simple-object-wizard.md)|  
|WMI 事件提供者|WMI 事件提供者精靈|  
|WMI 執行個體提供者|WMI 執行個體提供者精靈|  
  
### MFC  
  
|範本|精靈|  
|--------|--------|  
|MFC 類別|[MFC 加入類別精靈](../mfc/reference/mfc-add-class-wizard.md)|  
|來自 ActiveX 控制項的 MFC 類別|[加入來自 ActiveX 控制項的類別精靈](../ide/add-class-from-activex-control-wizard.md)|  
|TypeLib 的 MFC 類別|[從 Typelib 加入類別精靈](../mfc/reference/add-class-from-typelib-wizard.md)|  
|MFC ODBC 消費者|[MFC ODBC 消費者精靈](../mfc/reference/mfc-odbc-consumer-wizard.md)|  
  
### 泛型類別  
  
|範本|精靈|  
|--------|--------|  
|泛型 C\+\+ 類別|[泛型 C\+\+ 類別精靈](../ide/generic-cpp-class-wizard.md)|  
  
## 請參閱  
 [加入成員函式](../ide/adding-a-member-function-visual-cpp.md)   
 [加入成員變數](../ide/adding-a-member-variable-visual-cpp.md)   
 [覆寫 Virtual 函式](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC 訊息處理常式](../mfc/reference/adding-an-mfc-message-handler.md)   
 [巡覽類別結構](../ide/navigating-the-class-structure-visual-cpp.md)