---
title: "使用 wmain | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "wmain 函式"
ms.assetid: d0300812-adc4-40c6-bba3-b2da25468c80
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 使用 wmain
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 特定的**  
  
 在 Unicode 程式設計模型中，您可以定義寬字元版本的 **main** 函式。  如果您要撰寫遵守 Unicode 程式設計模型的可攜式程式碼，請使用 **wmain** 而非 **main**。  
  
## 語法  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
## 備註  
 您可以使用類似於 **main** 的格式將形式參數宣告為 **wmain**。  然後您可以傳遞寬字元引數以及 \(選擇性的\) 一個指向程式的寬字元環境指標。  **wmain** 的 `argv` 和 `envp` 參數都是 `wchar_t*` 型別。  例如：  
  
 如果您的程式使用 **main** 函式，則多位元組字元環境就會在程式啟動時由 Run\-Time 程式庫建立。  環境的寬字元複本只有在需要時才建立 \(例如，藉著呼叫 `_wgetenv` 或 `_wputenv` 函式\)。  在第一次呼叫 `_wputenv` 時，或在第一次呼叫 `_wgetenv` 時，如果 MBCS 環境已經存在，則會建立對應的寬字元字串環境，然後再由 `_wenviron` 全域變數 \(是 `_environ` 全域變數的寬字元版本\) 指向該變數。  此時會同時存在兩個環境 \(MBCS 和 Unicode\) 的複本，並由作業系統在整個程式存留期裡進行維護。  
  
 同樣的，如果您的程式使用 **wmain** 函式，寬字元環境在程式啟動時建立，並且由 `_wenviron` 全域變數指著。  MBCS \(ASCII\) 環境是在第一次呼叫 `_putenv` 或 `getenv` 時建立的，並且由 `_environ` 全域變數指向。  
  
 如需有關 MBCS 環境的詳細資訊，請參閱《執行階段程式庫參考》中的[國際化](../c-runtime-library/internationalization.md)。  
  
 **END Microsoft 特定的**  
  
## 請參閱  
 [main 函式和程式執行](../c-language/main-function-and-program-execution.md)