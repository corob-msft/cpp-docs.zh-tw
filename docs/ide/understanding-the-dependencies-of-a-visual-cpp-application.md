---
title: "了解 Visual C++ 應用程式的相依性 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "應用程式部署 [C++], 相依性"
  - "相依性 [C++], 應用程式部署和"
  - "Dependency Walker"
  - "depends.exe"
  - "部署應用程式 [C++], 相依性"
  - "DLL [C++], 相依性"
  - "DUMPBIN 公用程式"
  - "程式庫 [C++], 應用程式部署問題"
ms.assetid: 62a44c95-c389-4c5f-82fd-07d7ef09dbf9
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 了解 Visual C++ 應用程式的相依性
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

若要判斷應用程式相依於哪些 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 程式庫，您可以檢視專案屬性   \(在 \[方案總管\] 中，以滑鼠右鍵按一下專案，並選擇 \[屬性\] 開啟 \[屬性頁\] 對話方塊\)。 您也可以使用 Dependency Walker \(depends.exe\)，更全面性地了解相依性。  
  
 在 \[**屬性頁**\] 對話方塊中，您可以在 \[**組態屬性**\] 下檢查各種頁面以了解相依性。  例如，如果您的專案使用 MFC 程式庫，而您在 \[一般\] 頁面的 \[組態屬性\] 上選擇 \[使用 MFC 的共用 DLL\] 的 \[MFC 的使用\]，您的應用程式在執行階段會相依於 MFC DLL，如 mfc\<version\>.dll。  如果應用程式不使用 MFC，而且您在 \[**程式碼產生**\] 頁面的 \[**C\/C\+\+**\] 的 \[**組態屬性**\] 上選擇 \[**多執行緒偵錯 DLL \(\/MDd\)**\] 或 \[**多執行緒 DLL \(\/MD\)**\] 的 \[**執行階段程式庫**\] 值，則應用程式可能會相依於 CRT 程式庫。  
  
 判斷應用程式相依於哪些 DLL 的一個更簡單方法，就是使用 Dependency Walker \(depends.exe\) 開啟應用程式。  您可以從 [Dependency Walker](http://go.microsoft.com/fwlink/p/?LinkId=132640) 網站下載這個工具。  
  
 您可以使用 depends.exe 檢查在載入期間連結應用程式的 DLL 清單，以及其延遲載入 DLL 的清單。  如果您要取得在執行階段動態載入的完整 DLL 清單，您可以使用 depends.exe 中的程式碼剖析功能測試應用程式，直到您確定所有程式碼路徑皆已執行為止。  當您結束程式碼剖析工作階段時，depends.exe 將會顯示已於執行階段動態載入的 DLL。  
  
 在您使用 depends.exe 時，請注意 DLL 可能會相依於另一個 DLL 或特定版本的 DLL。  您可在開發電腦或目標電腦上使用 depends.exe。  在開發電腦上，depends.exe 將會報告支援應用程式所需的 DLL。  如果您在目標電腦上執行應用程式時遇到問題，您可將 depends.exe 複製到該電腦並且在工具中開啟應用程式，藉以判斷是否有缺少任何必要的 DLL 或有不正確的 DLL。  
  
 當您知道應用程式所相依的 DLL，您可以判斷當部署到另一部電腦時，必須要與應用程式一起轉散發的 DLL。  在大多數情況下，您不需要轉散發系統 DLL，但是可能必須轉散發 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 程式庫的 DLL。  如需詳細資訊，請參閱[決定要轉散發哪些 DLL](../ide/determining-which-dlls-to-redistribute.md)。  
  
## 請參閱  
 [部署桌面應用程式](../ide/deploying-native-desktop-applications-visual-cpp.md)