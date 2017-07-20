---
title: "如何：使用 /clr 編譯 MFC 和 ATL 程式碼 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr 編譯器選項 [C++], 編譯 ATL 和 MFC 程式碼"
  - "ATL [C++], 互通性"
  - "擴充 DLL [C++], /clr 編譯器選項"
  - "Interop [C++], /clr 編譯器選項"
  - "互通性 [C++], /clr 編譯器選項"
  - "MFC [C++], 互通性"
  - "混合的組件 [C++], ATL 程式碼"
  - "混合的組件 [C++], MFC 程式碼"
  - "標準 DLL [C++], /clr 編譯器選項"
ms.assetid: 12464bec-33a4-482c-880a-c078de7f6ea5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 如何：使用 /clr 編譯 MFC 和 ATL 程式碼
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

本主題將討論如何編譯現有的 MFC 和 ATL 程式，使其以 Common Language Runtime 為目標。  
  
### 若要使用 \/clr 編譯 MFC 可執行檔或標準 DLL  
  
1.  在 \[**方案總管**\] 中，以滑鼠右鍵按一下專案，然後按一下 \[**內容**\]。  
  
2.  在 \[**專案屬性頁**\] 對話方塊中，展開 \[**組態屬性**\] 旁的節點，然後選取 \[**一般**\]。  在右窗格中的 \[**專案預設值**\] 底下，將 \[**Common Language Runtime 支援**\] 設定為 \[**Common Language Runtime 支援 \(\/clr\)**\]。  
  
     在同一個窗格中，確定 \[**MFC 的使用**\] 已設定為 \[**使用 MFC 的共用 DLL**\]。  
  
3.  請在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**一般**\]。  確定 \[**偵錯資訊格式**\] 已設定為 \[**程式資料庫 \/Zi**\] \(不是 **\/ZI**\)。  
  
4.  選取 \[**程式碼產生**\] 節點。  將 \[**啟用最少重建**\] 設定為 \[**否 \(\/Gm\-\)**\]。  並且將 \[**基礎執行階段檢查**\] 設定為 \[**預設值**\]。  
  
5.  在 \[**組態屬性**\] 底下，選取 \[**C\/C\+\+**\]，再選取 \[**程式碼產生**\]。  確定 \[**執行階段程式庫**\] 已設定為 \[**多執行緒偵錯 DLL \(\/MDd\)**\] 或 \[**多執行緒 DLL \(\/MD\)**\]。  
  
6.  在 Stdafx.h 中，加入下列程式碼行。  
  
    ```  
    #using <System.Windows.Forms.dll>  
    ```  
  
### 若要使用 \/clr 編譯 MFC 擴充 DLL  
  
1.  請依照＜若要使用 \/clr 編譯 MFC 可執行檔或標準 DLL＞一節中的步驟進行。  
  
2.  在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**先行編譯標頭檔**\]。  將 \[**建立\/使用先行編譯標頭檔**\] 設定為 \[**未使用先行編譯標頭檔**\]。  
  
     或者，在 \[**方案總管**\] 中，以滑鼠右鍵按一下 Stdafx.cpp，然後按一下 \[**屬性**\]。  請在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**一般**\]。  將 \[**使用 Common Language Runtime 支援編譯**\] 設定為 \[**不支援 Common Language Runtime**\]。  
  
3.  針對包含 DllMain 及其呼叫之任何項目的檔案，在 \[**方案總管**\] 中，以滑鼠右鍵按一下檔案並選取 \[**屬性**\]。  請在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**一般**\]。  在右窗格中的 \[**專案預設值**\] 底下，將 \[**使用 Common Language Runtime 支援編譯**\] 設定為 \[**不支援 Common Language Runtime**\]。  
  
### 若要使用 \/clr 編譯 ATL 可執行檔  
  
1.  以滑鼠右鍵按一下 \[**方案總管**\] 中的專案，然後按一下 \[**屬性**\]。  
  
2.  在 \[**專案屬性頁**\] 對話方塊中，展開 \[**組態屬性**\] 旁的節點，然後選取 \[**一般**\]。  在右窗格中的 \[**專案預設值**\] 底下，將 \[**Common Language Runtime 支援**\] 設定為 \[**Common Language Runtime 支援 \(\/clr\)**\]。  
  
3.  請在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**一般**\]。  確定 \[**偵錯資訊格式**\] 已設定為 \[**程式資料庫 \/Zi**\] \(不是 **\/ZI**\)。  
  
4.  選取 \[**程式碼產生**\] 節點。  將 \[**啟用最少重建**\] 設定為 \[**否 \(\/Gm\-\)**\]。  並且將 \[**基礎執行階段檢查**\] 設定為 \[**預設值**\]。  
  
5.  在 \[**組態屬性**\] 底下，選取 \[**C\/C\+\+**\]，再選取 \[**程式碼產生**\]。  確定 \[**執行階段程式庫**\] 已設定為 \[**多執行緒偵錯 DLL \(\/MDd\)**\] 或 \[**多執行緒 DLL \(\/MD\)**\]。  
  
6.  針對每一個 MIDL 產生的檔案 \(C 檔案\)，在 \[**方案總管**\] 中，以滑鼠右鍵按一下檔案，然後按一下 \[**屬性**\]。  請在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**一般**\]。  將 \[**使用 Common Language Runtime 支援編譯**\] 設定為 \[**不支援 Common Language Runtime**\]。  
  
### 若要使用 \/clr 編譯 ATL DLL  
  
1.  請依照＜若要使用 \/clr 編譯 ATL 可執行檔＞一節中的步驟進行。  
  
2.  在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**先行編譯標頭檔**\]。  將 \[**建立\/使用先行編譯標頭檔**\] 設定為 \[**未使用先行編譯標頭檔**\]。  
  
     或者，在 \[**方案總管**\] 中，以滑鼠右鍵按一下 Stdafx.cpp，然後按一下 \[**屬性**\]。  請在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**一般**\]。  將 \[**使用 Common Language Runtime 支援編譯**\] 設定為 \[**不支援 Common Language Runtime**\]。  
  
3.  針對包含 DllMain 及其呼叫之任何項目的檔案，在 \[**方案總管**\] 中，以滑鼠右鍵按一下檔案並選取 \[**屬性**\]。  請在 \[**組態屬性**\] 底下，展開 \[**C\/C\+\+**\] 旁的節點並選取 \[**一般**\]。  在右窗格中的 \[**專案預設值**\] 底下，將 \[**使用 Common Language Runtime 支援編譯**\] 設定為 \[**不支援 Common Language Runtime**\]。  
  
## 請參閱  
 [混合 \(原生和 Managed\) 組件](../dotnet/mixed-native-and-managed-assemblies.md)