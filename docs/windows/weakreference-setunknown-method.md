---
title: "WeakReference::SetUnknown 方法 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference::SetUnknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetUnknown 方法"
ms.assetid: 5dddb9e3-a7c1-4195-8166-97c5ab6e972f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# WeakReference::SetUnknown 方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

支援 WRL 結構，而且不能直接從您的程式碼使用。  
  
## <a name="syntax"></a>語法  
  
```  
void SetUnknown(  
   _In_ IUnknown* unk  
);  
```  
  
#### <a name="parameters"></a>參數  
 `unk`  
 指標 `IUnknown` 物件的介面。  
  
## <a name="remarks"></a>備註  
 設定目前的強式參考 `WeakReference` 物件與指定的介面指標。  
  
## <a name="requirements"></a>需求  
 **標頭︰** implements.h  
  
 **命名空間︰** Microsoft::WRL::Details  
  
## <a name="see-also"></a>另請參閱
[WeakReference 類別](../windows/weakreference-class1.md)  
 [Microsoft::WRL::Details 命名空間](../windows/microsoft-wrl-details-namespace.md)