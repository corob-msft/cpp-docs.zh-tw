---
title: satype （c + + COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 3d2d921e750adad0089df0d00590f256b56c732e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517685"
---
# <a name="satype"></a>satype

指定的資料型別`SAFEARRAY`結構。

## <a name="syntax"></a>語法

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>參數

*data_type*<br/>
資料型別`SAFEARRAY`做為參數傳遞至介面方法的資料結構。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|介面參數，介面方法|
|**可重複**|否|
|**必要屬性**|無|
|**無效屬性**|無|

## <a name="remarks"></a>備註

**Satype** c + + 屬性指定的資料型別`SAFEARRAY`。

> [!NOTE]
> 從卸除的間接取值層級`SAFEARRAY`從它在.cpp 檔案中的宣告方式產生的.idl 檔案中的指標。

## <a name="example"></a>範例

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>另請參閱

[編譯器屬性](compiler-attributes.md)<br/>
[參數屬性](parameter-attributes.md)<br/>
[方法屬性](method-attributes.md)<br/>
[id](id.md)