---
title: "try-finally 陳述式 (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "try_cpp"
  - "try"
  - "finally"
  - "finally_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__finally 關鍵字 [C]"
  - "__finally 關鍵字 [C], try-finally 陳述式語法"
  - "結構化例外狀況處理, try-finally"
  - "try-catch 關鍵字 [C]"
  - "try-catch 關鍵字 [C], try-finally 關鍵字 [C]"
  - "try-finally 關鍵字 [C]"
ms.assetid: 514400c1-c322-4bf3-9e48-3047240b8a82
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# try-finally 陳述式 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 特定的**  
  
 `try-finally` 陳述式是 C 語言的 Microsoft 擴充功能，可讓應用程式在執行程式碼的區塊遭到中斷時，保證會執行清除程式碼。  清除包含如取消配置記憶體、關閉檔案和釋放檔案控制代碼等工作。  `try-finally` 陳述式對於有多個地方要檢查可能會導致常式過早傳回的錯誤時會特別有用。  
  
 *try\-finally\-statement*：  
 **\_\_try**  *compound\-statement*  
  
 **\_\_finally**  *compound\-statement*  
  
 `__try` 子句後面的複合陳述式是保護的區段。  `__finally` 子句後面的複合陳述式則是終止處理常式。  處理常式會指定一組當保護區段結束時執行的動作、保護的區段是因例外狀況 \(異常終止\) 而結束，或依標準的執行順序 \(正常終止\) 而結束。  
  
 此時控制項會經由簡單的循序執行 \(正常執行\) 到達 `__try` 陳述式。  當控制項進入 `__try` 陳述式時，與其關聯的處理常式會變成作用中。  執行程序如下所示：  
  
1.  執行保護的區段。  
  
2.  已叫用終止處理常式。  
  
3.  當終止處理常式完成時，便會從 `__finally` 陳述式之後繼續執行。  不論保護的區段如何結束 \(例如，藉由保護主體外部的 `goto` 陳述式或是經由 `return` 陳述式\)，終止處理常式會在控制流程移出保護區段之前執行。  
  
 `__leave` 關鍵字在 `try-finally` 陳述式區塊內是有效的。  `__leave` 的作用是會跳到 `try-finally` 區塊的結尾。  接著便會立即執行終止處理常式。  雖然 `goto` 陳述式可用來達到相同的結果，但 `goto` 陳述式會造成堆疊回溯的情形。  因為不包含堆疊回溯，因此使用 `__leave` 陳述式會更有效率。  
  
 使用 `return` 陳述式或 `longjmp` 執行階段函式結束 `try-finally` 陳述式會視為是異常終止。  雖然不可跳入 `__try` 陳述式，但是可以從這類陳述式跳出。  起點和目的地之間的所有作用中 `__finally` 陳述式都必須執行。  這稱為「區域回溯」。  
  
 如果處理序在執行 `try-finally` 陳述式時遭到刪除，則不會呼叫終止處理常式。  
  
> [!NOTE]
>  結構化例外狀況處理可搭配 C 和 C\+\+ 原始程式檔使用。  不過，它不是專為 C\+\+ 所設計。  使用 C\+\+ 例外狀況處理可確保您的程式碼更具可移植性。  此外，C\+\+ 例外狀況處理機制更有彈性，因為它可以處理任何類型的例外狀況。  
  
> [!NOTE]
>  若是 C\+\+ 程式，則應該使用 C\+\+ 例外狀況處理，而不是結構化例外狀況處理。  如需詳細資訊，請參閱《C\+\+ 語言參考》中的[例外狀況處理](../cpp/exception-handling-in-visual-cpp.md)。  
  
 請參閱 [try\-except 陳述式](../c-language/try-except-statement-c.md)的範例，了解 `try-finally` 陳述式的運作方式。  
  
 **END Microsoft 特定的**  
  
## 請參閱  
 [try\-finally 陳述式](../cpp/try-finally-statement.md)