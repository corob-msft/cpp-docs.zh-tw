---
title: "_ATL_WIN_MODULE70 結構 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _ATL_WIN_MODULE70
- ATL::_ATL_WIN_MODULE70
- ATL._ATL_WIN_MODULE70
dev_langs:
- C++
helpviewer_keywords:
- _ATL_WIN_MODULE70 structure
- ATL_WIN_MODULE70 structure
ms.assetid: a0aaf3ea-ca77-46ec-bd53-4dfb61dffbea
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4e393abb2a904a0f5e101efe3d78d0645664397b
ms.openlocfilehash: 383384c8f08b98592f92b5d38850137c1c0c6d54
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="atlwinmodule70-structure"></a>_ATL_WIN_MODULE70 結構
ATL 中的視窗化程式碼使用  
  
## <a name="syntax"></a>語法  
  
```
struct _ATL_WIN_MODULE70 {
    UNIT cbSize; 
    CRITICAL_SECTION m_csWindowCreate;
    _AtlCreateWndData* m_pCreateWndList;
    CSimpleArray<ATOM> m_rgWindowClassAtoms;
};
```  
  
## <a name="members"></a>Members  
 `cbSize`  
 使用版本控制的結構大小。  
  
 `m_csWindowCreate`  
 用來序列化視窗註冊程式碼存取。 在內部使用 ATL  
  
 **m_pCreateWndList**  
 用來將 windows 繫結至其物件。 在內部使用 ATL  
  
 **m_rgWindowClassAtoms**  
 用來追蹤視窗類別註冊，讓它們可以適當地移除註冊在終止。 在內部使用 ATL  
  
## <a name="remarks"></a>備註  
 [_ATL_WIN_MODULE](atl-typedefs.md#_atl_win_module)定義為 typedef 的`_ATL_WIN_MODULE70`。  
  
## <a name="requirements"></a>需求  
 **標頭︰** atlbase.h  
  
## <a name="see-also"></a>另請參閱  
 [結構](../../atl/reference/atl-structures.md)





