---
title: "多重文件類型、檢視和框架視窗 | Microsoft Docs"
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
  - "靜態分隔視窗"
  - "多重檢視"
  - "多個文件類型"
  - "多個檢視, 框架視窗"
  - "文件類別, 多個"
  - "文件 [C++], 的多個類型"
  - "分隔視窗, 動態"
  - "動態分隔視窗"
  - "視窗 [C++], 動態分隔器"
  - "視窗 [C++], 靜態分隔器"
  - "多個框架視窗"
  - "分隔視窗, 靜態"
ms.assetid: c6b9e4e0-7c9c-45f1-a804-aeac39c9a128
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 多重文件類型、檢視和框架視窗
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Document\/View Creation](../mfc/document-view-creation.md) \(文件\/檢視建立\) 中描述文件、其檢視及其框架視窗之間的標準關聯性。 許多應用程式支援單一文件類型 \(但可能開啟該類型的多份文件\)，該類型具有單一文件檢視，而且每份文件只有一個框架視窗。 但有些應用程式可能需要更改一或多個預設。  
  
## 您還想知道關於哪些方面的詳細資訊？  
  
-   [多個文件類型](#_core_multiple_document_types)  
  
-   [多個檢視](#_core_multiple_views)  
  
-   [多個框架視窗](#_core_multiple_frame_windows)  
  
-   [分隔視窗](#_core_splitter_windows)  
  
##  <a name="_core_multiple_document_types"></a> 多個文件類型  
 \[MFC 應用程式精靈\] 為您建立單一文件類別。 不過在某些案例下，您可能需要支援多個文件類型。 例如，您的應用程式可能需要工作表和圖表文件。 每個文件類型會以其本身的文件類別表示，也可能以其本身的檢視類別表示。 當使用者選擇 \[開新檔案\] 命令時，此架構會顯示對話方塊，列出支援的文件類型。 然後根據使用者選擇的類型建立文件。 每個文件類型是由其本身的文件範本物件管理。  
  
 若要建立額外的文件類別，請參閱[加入類別](../ide/adding-a-class-visual-cpp.md)。 選擇 [CDocument](../mfc/reference/cdocument-class.md) 作為要從中衍生並提供所要求之文件資訊的類別類型。 然後實作新類別的資料。  
  
 若要讓架構知道此額外的文件類別，您必須將第二個呼叫加入應用程式類別之 [InitInstance](../Topic/CWinApp::InitInstance.md) 覆寫中的 [AddDocTemplate](../Topic/CWinApp::AddDocTemplate.md)。 如需詳細資訊，請參閱[文件範本](../mfc/document-templates-and-the-document-view-creation-process.md)。  
  
##  <a name="_core_multiple_views"></a> 多個檢視  
 許多文件只需要單一檢視，但也可能支援單一文件的多個檢視。 為了協助您實作多個檢視，文件物件保留一份自己的檢視清單、提供成員函式以加入及移除檢視，並提供 [UpdateAllViews](../Topic/CDocument::UpdateAllViews.md) 成員函式讓多個檢視知道文件資料何時變更。  
  
 MFC 支援相同文件上需要多個檢視的三種常見使用者介面。 這些模式包括︰  
  
-   檢視相同類別的物件，每個物件在不同的 MDI 文件框架視窗中。  
  
     您可能想要支援在文件上建立第二個框架視窗。 使用者可以選擇 \[開新視窗\] 命令，以開啟第二個具有相同文件檢視的框架，然後使用這兩個框架同時檢視文件的不同部分。 此架構透過複製附加至文件的初始框架視窗和檢視，來支援對 MDI 應用程式使用 \[視窗\] 功能表上的 \[開新視窗\] 命令。  
  
-   檢視相同文件框架視窗中相同類別的物件。  
  
     分隔視窗會將單一文件視窗的檢視空間，分隔成文件的多個不同檢視。 此架構會從相同檢視類別建立多個檢視物件。 如需詳細資訊，請參閱[分隔視窗](#_core_splitter_windows)。  
  
-   檢視單一框架視窗中不同類別的物件。  
  
     在此分隔視窗變化模型中，多個檢視會共用單一框架視窗。 這些檢視是從不同類別建構，每個檢視提供不同方式來檢視相同文件。 例如，一個檢視可能以標準模式顯示文書處理文件，而另一個檢視則以大綱模式顯示相同文件。 分隔器控制項可讓使用者調整檢視的相對大小。  
  
 下圖分成 a、b 和 c 部分，並依上述順序顯示三種使用者介面模型。  
  
 ![多重檢視使用者介面](../mfc/media/vc37a71.png "vc37A71")  
多個檢視使用者介面  
  
 此架構透過實作 \[開新視窗\] 命令及提供 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md) 類別，來提供這些模型 \(如[分隔視窗](#_core_splitter_windows)中所述\)。 您可以使用這些模型作為起點，來實作其他模型。 如需說明檢視、框架視窗和分隔器之不同組態的範例程式，請參閱 [MFC 範例](../top/visual-cpp-samples.md)。  
  
 如需 `UpdateAllViews` 的詳細資訊，請參閱＜MFC 參考＞中的 [CView 類別](../mfc/reference/cview-class.md)和 [Scribble 範例](../top/visual-cpp-samples.md)。  
  
##  <a name="_core_multiple_frame_windows"></a> 多個框架視窗  
 您可以對 MDI 應用程式使用 \[視窗\] 功能表上的 \[開新視窗\] 命令，在相同文件上建立第二個框架視窗。 如需詳細資訊，請參閱[多個檢視使用者介面](#_core_multiple.2d.view_user_interfaces)圖中的第一個模型。  
  
##  <a name="_core_splitter_windows"></a> 分隔視窗  
 在分隔視窗中，視窗會 \(或可以\) 分隔成兩個或多個可捲動的窗格。 捲軸旁之視窗框架中的分隔器控制項 \(或「分隔方塊」\)，可讓使用者調整窗格的相對大小。 每個窗格是相同文件的檢視。 在「動態」分隔器中，檢視屬於相同類別，如[多個檢視使用者介面](#_core_multiple.2d.view_user_interfaces)圖的 b 部分所示。 在「靜態」分隔器中，檢視可以屬於不同類別。[CSplitterWnd](../mfc/reference/csplitterwnd-class.md) 類別支援這兩種類型的分隔視窗。  
  
 動態分隔視窗具有相同類別的檢視，可讓使用者隨意將視窗分隔成多個窗格，然後捲動不同窗格以查看文件的不同部分。 使用者也可以取消分隔視窗，以移除其他檢視。 加入 [Scribble 範例](../top/visual-cpp-samples.md)中的分隔視窗即為一例。 該主題描述建立動態分隔視窗的技術。[多個檢視使用者介面](#_core_multiple.2d.view_user_interfaces)圖的 b 部分顯示動態分隔視窗。  
  
 靜態分隔視窗具有不同類別的檢視，視窗一開始就分隔成多個窗格，每個窗格各有不同用途。 例如，在 Visual C\+\+ 點陣圖編輯器中，影像視窗並排顯示兩個窗格。 左窗格顯示實際大小的點陣圖影像。 右窗格顯示縮小或放大的相同點陣圖影像。 這兩個窗格是以「分隔列」隔開，使用者可加以拖曳來變更窗格的相對大小。[多個檢視使用者介面](#_core_multiple.2d.view_user_interfaces)圖的 c 部分顯示靜態分隔視窗。  
  
 如需詳細資訊，請參閱＜MFC 參考＞中的 [CSplitterWnd 類別](../mfc/reference/csplitterwnd-class.md)和 [MFC 範例](../top/visual-cpp-samples.md)。  
  
## 請參閱  
 [文件\/檢視架構](../mfc/document-view-architecture.md)