---
title: "InterfaceTraits::CastToBase 方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits::CastToBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CastToBase 方法"
ms.assetid: 0591a017-0adf-4358-b946-eb0a307ce7f2
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# InterfaceTraits::CastToBase 方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

支援 WRL 基礎結構，而且不是為了要直接從您的程式碼中使用而設計。  
  
## 語法  
  
```  
template<  
   typename T  
>  
static __forceinline Base* CastToBase(  
   _In_ T* ptr  
);  
```  
  
#### 參數  
 `T`  
 `ptr` 參數的型別。  
  
 `ptr`  
 型別 `T`的指標。  
  
## 傳回值  
 為 `Base`的指標。  
  
## 備註  
 轉型指定指標為 `Base`的指標。  
  
 如需 `Base`的詳細資訊，請參閱 [InterfaceTraits 結構](../windows/interfacetraits-structure.md)的公用 Typedefs 部分。  
  
## 需求  
 **標題:** implements.h  
  
 **命名空間：** Microsoft::WRL::Details  
  
## 請參閱  
 [InterfaceTraits 結構](../windows/interfacetraits-structure.md)   
 [Microsoft::WRL::Details 命名空間](../windows/microsoft-wrl-details-namespace.md)