---
title: InspectableClass 巨集
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::InspectableClass
ms.assetid: ff390b26-58cc-424f-87ac-1fe3cc692b59
ms.openlocfilehash: cedf395ae98a423e0335851327b5fdda1a4bc7d6
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893271"
---
# <a name="inspectableclass-macro"></a>InspectableClass 巨集

設定執行階段類別名稱和信任層級。

## <a name="syntax"></a>語法

```cpp
InspectableClass(
   runtimeClassName,
   trustLevel)
```

### <a name="parameters"></a>參數

*runtimeClassName*<br/>
執行階段類別的完整文字名稱。

*trustLevel*<br/>
其中一個[TrustLevel](/windows/desktop/api/inspectable/ne-inspectable-trustlevel)列舉值。

## <a name="remarks"></a>備註

**InspectableClass**巨集只能搭配 Windows 執行階段類型。

## <a name="requirements"></a>需求

**標頭：** implements.h

**命名空間：** Microsoft:: wrl

## <a name="see-also"></a>另請參閱

[RuntimeClass 類別](runtimeclass-class.md)