---
title: RemoveIUnknown 類別
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::RemoveIUnknown
ms.assetid: 998e711a-7d1a-44c6-a016-e6167aa40863
ms.openlocfilehash: bfe397f64650caedab1408f1f74fabd005dd98cf
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336094"
---
# <a name="removeiunknown-class"></a>RemoveIUnknown 類別

支援 WRL 結構，而且不是直接從您的程式碼使用。

## <a name="syntax"></a>語法

```cpp
template <typename T>
struct RemoveIUnknown;

template <typename T>
class RemoveIUnknown : public T;
```

### <a name="parameters"></a>參數

*T*<br/>
類別中。

## <a name="remarks"></a>備註

建立類型，相當於`IUnknown`為基礎的類型，但有非虛擬`QueryInterface`， `AddRef`，和`Release`成員函式。

根據預設，COM 方法提供虛擬`QueryInterface`， `AddRef`，和`Release`方法。 不過，`ComPtr`不需要虛擬方法的額外負荷。 `RemoveIUnknown` 藉由提供私用、 非虛擬消除該額外負荷`QueryInterface`， `AddRef`，和`Release`方法。

## <a name="members"></a>成員

### <a name="public-typedefs"></a>公用 Typedefs

|名稱|描述|
|----------|-----------------|
|`ReturnType`|相當於範本參數類型的同義字*T*但有非虛擬`IUnknown`成員。|

## <a name="inheritance-hierarchy"></a>繼承階層

`T`

`RemoveIUnknown`

## <a name="requirements"></a>需求

**標頭：** client.h

**命名空間：** Microsoft::WRL::Details

## <a name="see-also"></a>另請參閱

[Microsoft::WRL::Details 命名空間](microsoft-wrl-details-namespace.md)