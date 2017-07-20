---
title: "WeakReference::IncrementStrongReference 方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncrementStrongReference 方法"
ms.assetid: d0232426-a8cb-48b4-99d4-165de2d66cb9
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# WeakReference::IncrementStrongReference 方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

支援 WRL 結構，而且不能直接從您的程式碼使用。  
  
## <a name="syntax"></a>語法  
  
```  
ULONG IncrementStrongReference();  
```  
  
## <a name="return-value"></a>傳回值  
 遞增的強式參考計數。  
  
## <a name="remarks"></a>備註  
 目前的 WeakReference 物件的強式參考計數遞增。  
  
## <a name="requirements"></a>需求  
 **標頭︰** implements.h  
  
 **命名空間︰** Microsoft::WRL::Details  
  
## <a name="see-also"></a>另請參閱  
[WeakReference 類別](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 命名空間](../windows/microsoft-wrl-details-namespace.md)