---
title: "/HIGHENTROPYVA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/HIGHENTROPYVA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/HIGHENTROPYVA editbin 選項"
  - "HIGHENTROPYVA editbin 選項"
  - "-HIGHENTROPYVA editbin 選項"
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /HIGHENTROPYVA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定可執行檔映像是否支援高熵 64 位元位址空間配置隨機載入 \(ASLR\)。  
  
```  
  
/HIGHENTROPYVA[:NO]  
  
```  
  
## 備註  
 此選項會修改 .dll 檔或 .exe 檔的標頭，以指示是否支援 64 位元位址的 ASLR。  在可執行檔和它所依據的所有模組上設定此選項時，支援 64 位元 ASLR 的作業系統可以使用 64 位元虛擬位址空間中的隨機位址，在載入時間為可執行檔映像的區段重定基底。  這個大型位址空間會使攻擊者較難猜到特定記憶體區域的位置。  
  
 根據預設，連結器會為 64 位元可執行檔映像設定此選項。  若要設定此選項，必須同時設定 [\/DYNAMICBASE](../../build/reference/dynamicbase.md) 選項。  
  
## 請參閱  
 [EDITBIN 選項](../../build/reference/editbin-options.md)   
 [\/DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Windows ISV 軟體安全性防禦措施](http://msdn.microsoft.com/library/bb430720.aspx)