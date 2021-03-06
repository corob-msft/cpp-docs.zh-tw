---
title: 物件狀態巨集
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 9c4df80b2b9828077ec3738bc296f19aadf2df68
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658948"
---
# <a name="object-status-macros"></a>物件狀態巨集

這個巨集設定屬於 ActiveX 控制項的旗標。

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|用於 ATL ActiveX 控制項，以設定 OLEMISC 旗標。|

## <a name="requirements"></a>需求

**標頭：** atlcom.h

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS

用於 ATL ActiveX 控制項，以設定 OLEMISC 旗標。

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>參數

*miscstatus*<br/>
所有適用的 OLEMISC 旗標。

### <a name="remarks"></a>備註

這個巨集用來設定 ActiveX 控制項的 OLEMISC 旗標。 請參閱[IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus)如需詳細資訊。

### <a name="example"></a>範例

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>另請參閱

[巨集](../../atl/reference/atl-macros.md)
