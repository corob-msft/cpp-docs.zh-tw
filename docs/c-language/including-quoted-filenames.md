---
title: "包含加引號的檔案名稱 | Microsoft Docs"
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
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 包含加引號的檔案名稱
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2**：針對可包含的原始程式檔支援以引號括住的名稱  
  
 如果您以兩組雙引號 \(" "\) 指定 Include 檔完整明確的路徑規格，前置處理器只會搜尋該路徑規格並忽略標準目錄。  
  
 當 Include 檔指定為 [\#include](../preprocessor/hash-include-directive-c-cpp.md) "path\-spec" 時，目錄搜尋會先從父檔案的目錄開始，繼續進行到其上二層檔案的目錄。  因此，搜尋會從包含處理中原始程式檔的目錄相對位置開始進行。  如果沒有上二層檔案，也找不到此檔案，則會繼續搜尋，如同以角括弧括住檔案名稱一般。  
  
## 請參閱  
 [前置處理指示詞](../c-language/preprocessing-directives.md)