---
title: 版本 （c + + COM 屬性）
ms.date: 10/02/2018
f1_keywords:
- vc-attr.version
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
ms.openlocfilehash: 01c4cca846326d237fdacd19187a44e21bd15913
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519310"
---
# <a name="version-c"></a>version (C++)

識別類別的多個版本之間的特定版本。

## <a name="syntax"></a>語法

```cpp
[ version("version") ]
```

### <a name="parameters"></a>參數

*version*<br/>
版本號碼`coclass`。 如果未指定，1.0 會置於.idl 檔案。

## <a name="remarks"></a>備註

**版本**c + + 屬性具有相同的功能[版本](/windows/desktop/Midl/version)MIDL 屬性且會傳遞至產生的.idl 檔案。

## <a name="example"></a>範例

請參閱[可繫結](bindable.md)的範例使用的範例**版本**。

## <a name="requirements"></a>需求

### <a name="attribute-context"></a>屬性內容

|||
|-|-|
|**適用於**|**類別**，**結構**|
|**可重複**|否|
|**必要屬性**|**coclass**|
|**無效屬性**|無|

如需有關屬性內容的詳細資訊，請參閱 [屬性內容](cpp-attributes-com-net.md#contexts)。

## <a name="see-also"></a>另請參閱

[編譯器屬性](compiler-attributes.md)<br/>
[類別屬性](class-attributes.md)