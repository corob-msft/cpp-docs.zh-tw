---
title: "彙總 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.aggregates"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregates 屬性"
  - "彙總 [C++]"
  - "彙總物件 [C++], aggregates 屬性"
  - "彙總 [C++]"
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 彙總
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

表示物件會彙總 CLSID 所指定的物件。  
  
## 語法  
  
```  
  
[ aggregates(  
clsid,  
variable_name  
) ]  
  
```  
  
#### 參數  
 `clsid`  
 指定可彙總物件的 CLSID。  
  
 `variable_name`  
 要插入的變數名稱。 此變數包含所彙總物件的 **IUnknown**。  
  
## 備註  
 套用至物件時，**aggregates** C\+\+ 屬性會實作所彙總物件的外部包裝函式 \(透過 `clsid` 所指定\)。  
  
 此屬性需要 [coclass](../windows/coclass.md)、[progid](../windows/progid.md) 或 [vi\_progid](../windows/vi-progid.md) 屬性 \(或表示上述其中一項的另一個屬性\) 也套用至相同的項目。 如果使用任何單一屬性，則會自動套用其他兩項。 例如，如果套用 **progid**，則也會套用 **vi\_progid** 和 **coclass**。  
  
 **ATL 專案**  
  
 如果在使用 ATL 的專案內使用此屬性，則屬性的行為會變更。 首先，會在目標物件的 COM 對應中新增下列項目︰  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 其次，也會新增 [DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md) 巨集。  
  
## 範例  
  
```  
// cpp_attr_ref_aggregates.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
// requires 'aggregatable.dll'  
// see aggregatable attribute to create 'aggregatable.dll'  
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;  
  
[module (name="MYObject")];  
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]  
__interface IObject  
{  
};  
  
[ coclass, aggregates(__uuidof(CMyClass)),   
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]  
struct CObject : IObject  
{  
   int i;  
};  
```  
  
## 需求  
  
### 屬性內容  
  
|||  
|-|-|  
|**適用於**|**class**、`struct`|  
|**可重複**|是|  
|**必要屬性**|下列一或多個項目：**coclass**、**progid** 或 **vi\_progid**。|  
|**無效屬性**|無|  
  
 如需有關屬性內容的詳細資訊，請參閱[屬性內容](../windows/attribute-contexts.md)。  
  
## 請參閱  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [彙總](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [可彙總](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)   
 [Attributes Samples](http://msdn.microsoft.com/zh-tw/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)