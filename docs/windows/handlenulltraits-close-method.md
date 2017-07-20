---
title: "HANDLENullTraits::Close 方法 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close 方法"
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HANDLENullTraits::Close 方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

關閉指定的控制代碼。  
  
## 語法  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### 參數  
 `h`  
 關閉的控制代碼。  
  
## 傳回值  
 **true** ，如果控制代碼 `h` 成功關閉，否則， **false**。  
  
## 需求  
 **標題:** corewrappers.h  
  
 **命名空間:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 請參閱  
 [HANDLENullTraits 結構](../windows/handlenulltraits-structure.md)