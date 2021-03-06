---
title: Platform::Metadata::DefaultMemberAttribute 屬性
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::DefaultMemberAttribute
helpviewer_keywords:
- Platform::Metadata::DefaultMemberAttribute Attribute
ms.assetid: d8abda01-c257-4371-aec4-541d4825e0af
ms.openlocfilehash: a4b3d5e8ab5d6ce254560bc84daceac74e2c9ca1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486654"
---
# <a name="platformmetadatadefaultmemberattribute-attribute"></a>Platform::Metadata::DefaultMemberAttribute 屬性

指出在許多可能的多載函式中要叫用的慣用函式。

## <a name="syntax"></a>語法

```cpp
public ref class DefaultMember abstract : Attribute
```

## <a name="inheritance"></a>繼承

[Platform::Object](../cppcx/platform-object-class.md)

[Platform::Metadata::Attribute](../cppcx/platform-metadata-attribute-attribute.md)

### <a name="remarks"></a>備註

將 DefaultMember 屬性套用至 JavaScript 應用程式將取用的方法。

### <a name="requirements"></a>需求

**最低支援用戶端：** Windows 8

**最低支援伺服器：** Windows Server 2012

**命名空間：** Platform::Metadata

**中繼資料：** platform.winmd

## <a name="see-also"></a>另請參閱

[Platform::Metadata 命名空間](../cppcx/platform-metadata-namespace.md)