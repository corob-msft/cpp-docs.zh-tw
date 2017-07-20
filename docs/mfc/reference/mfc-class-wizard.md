---
title: "MFC 類別精靈 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.wizards.classwizard"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC 類別精靈"
  - "精靈 (MFC)"
ms.assetid: 8b0dd867-5d07-4214-99be-2a1c1995e6d9
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MFC 類別精靈
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

可讓您將訊息和訊息處理常式加入至專案中的類別。  您也可以啟動其他精靈或將類別加入至您的專案。  
  
 若要開啟 \[**MFC 類別精靈**\]，請按一下 \[**專案**\] 功能表上的 \[**類別精靈**\]。  若要以鍵盤快速鍵開啟精靈，請按下 CTRL\+SHIFT\+X。  
  
## UIElement 清單  
 **專案**  
 在您方案中之專案的名稱。  
  
 您可以從下拉式清單方塊選取方案中的其他專案。  
  
 **類別名稱**  
 專案中類別的名稱。  
  
 當您在 \[**類別名稱**\] 清單中選取類別時，類就會在 \[**MFC 類別精靈**\] 的控制項中填入該類別的資料。  當您變更控制項的值時，選取類別中的資料會受到影響。  
  
 **加入類別**  
 可讓您從數個來源之一加入類別。  
  
 根據您的選取範圍，啟動 \[**MFC 加入類別精靈**\]、\[**從 Typelib 加入類別精靈**\]、\[**從 ActiveX 控制項加入類別精靈**\] 或 \[**MFC ODBC 消費者精靈**\]。  
  
 **基底類別**  
 顯示在 \[**類別名稱**\] 之類別的基底類別。  
  
 **類別宣告**  
 在其中宣告 \[**類別名稱**\] 類別的類別。  
  
 只有 \[**類別宣告**\] 方塊中的名稱不同於 \[**類別實作**\] 方塊中的名稱時，才會顯示該方塊。  
  
 **資源**  
 \[**類別名稱**\] 中的資源的識別碼 \(如果有的話\)。  否則，\[**資源**\] 方塊是空的。  
  
 **類別實作**  
 檔案的名稱，該檔案包含 \[**類別名稱**\] 中之類別的實作。  
  
 您可以按一下箭號來選取不同的實作檔。  下表列出可用的選項。  
  
|選項|說明|  
|--------|--------|  
|**Open File**|結束類別精靈，並且開啟目前的類別實作檔案。|  
|**開啟包含資料夾**|開啟包含目前類別實作檔的資料夾。|  
|**將完整路徑複製到剪貼簿**|將將目前實作檔的路徑複製到剪貼簿。|  
  
 **命令**  
 可讓您加入、刪除、編輯或搜尋命令和其訊息處理常式。  
  
 若要加入處理常式，請按一下 \[**加入處理常式**\]，或按兩下 \[**物件 ID**\] 清單 或 \[**訊息**\] 清單中的項目。  所產生的函式名稱、ID 和訊息會顯示在 \[**成員函式** \] 清單中。  
  
 若要刪除處理常式，請選取 \[**成員函式**\] 清單中的項目，然後按一下 \[**刪除處理常式**\]。  
  
 若要修改處理常式，請在 \[**成員函式**\] 清單中連按兩下對應的項目。  或者，選取清單方塊中的一個項目，然後按一下 \[**編輯程式碼**\]。  
  
 **訊息**  
 可讓您加入、刪除、編輯或搜尋訊息和其訊息處理常式。  
  
 若要加入處理常式，請按一下 \[**加入處理常式**\]，或按兩下 \[**訊息**\] 清單中的項目。  
  
 若要加入自訂的訊息，請按一下 \[**加入自訂訊息**\] 或按 Enter 鍵，然後在 \[**加入自訂訊息**\] 對話方塊中指定值。  在該對話方塊中，您也可以選取 \[**註冊訊息**\] 來處理新的視窗訊息，確保這個訊息在整個作業系統中都是唯一的。  
  
 **虛擬函式**  
 可讓您加入、刪除、編輯或搜尋虛擬函式或覆寫的虛擬函式。  
  
 **成員變數**  
 可讓您加入、刪除、編輯或搜尋成員變數。  
  
 **方法**  
 可讓您加入、刪除或搜尋方法，同時移至方法的定義或宣告。  
  
 若要加入方法，請按一下 \[**加入方法**\]，然後在 \[**加入方法**\] 對話方塊中指定值。  
  
 若要刪除方法，請選取 \[**方法**\] 清單中的項目，然後按一下 \[**刪除方法**\]。  
  
 若要顯示宣告，請選取 \[**方法**\] 清單中的項目，再按 \[**移至宣告**\]。  
  
 若要顯示定義，請按兩下 \[**方法**\] 清單中的項目。  或者，選取 \[**方法**\] 清單中的一個項目，然後按一下 \[**移至定義**\] 按鈕。  
  
## 請參閱  
 [加入類別](../../ide/adding-a-class-visual-cpp.md)