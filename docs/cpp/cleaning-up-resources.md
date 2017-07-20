---
title: "清除資源 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C++ 例外狀況處理, 終止處理常式"
  - "例外狀況處理, 清除資源"
  - "例外狀況處理, 清除程式碼"
  - "資源 [C++], 清除"
  - "終止處理常式, 清除資源"
  - "try-catch 關鍵字 [C++], 終止處理常式"
ms.assetid: 65753efe-6a27-4750-b90c-50635775c1b6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 清除資源
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

在終止處理常式執行期間，您可能不知道在呼叫終止處理常式之前實際配置了哪些資源。  有可能在配置所有資源之前，`__try` 陳述式區塊就已中斷，此時並非所有資源皆已開啟。  
  
 因此，為了安全起見，您應該先檢查哪些資源已實際開啟，再繼續進行終止處理的清除作業。  建議的程序是：  
  
1.  將控制代碼初始化為 NULL。  
  
2.  在 `__try` 陳述式區塊中配置資源。  資源一配置，控制代碼就會設定為正值。  
  
3.  在 `__finally` 陳述式區塊中，釋放對應控制代碼或旗標變數為非零或非 NULL 的每個資源。  
  
## 範例  
 例如，下列程式碼會使用終止處理常式關閉三個檔案和一個在 `__try` 陳述式區塊中配置的記憶體區塊。  在清除資源之前，程式碼會先檢查資源是否已配置。  
  
```  
// exceptions_Cleaning_up_Resources.cpp  
#include <stdlib.h>  
#include <malloc.h>  
#include <stdio.h>  
#include <windows.h>  
  
void fileOps() {  
   FILE  *fp1 = NULL,  
         *fp2 = NULL,  
         *fp3 = NULL;  
   LPVOID lpvoid = NULL;  
   errno_t err;  
  
   __try {  
      lpvoid = malloc( BUFSIZ );  
  
      err = fopen_s(&fp1, "ADDRESS.DAT", "w+" );  
      err = fopen_s(&fp2, "NAMES.DAT", "w+" );  
      err = fopen_s(&fp3, "CARS.DAT", "w+" );  
   }  
   __finally {  
      if ( fp1 )  
         fclose( fp1 );  
      if ( fp2 )  
         fclose( fp2 );  
      if ( fp3 )  
         fclose( fp3 );  
      if ( lpvoid )  
         free( lpvoid );  
   }  
}  
  
int main() {  
   fileOps();  
}  
```  
  
## 請參閱  
 [撰寫終止處理常式](../cpp/writing-a-termination-handler.md)   
 [結構化例外狀況處理](../cpp/structured-exception-handling-c-cpp.md)