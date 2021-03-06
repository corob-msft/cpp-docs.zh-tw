---
title: SemaphoreTraits 結構
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: e7bd2e5d0993c8e4be7223d98ffb1dbec14cbb74
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336381"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits 結構

定義通用特性`Semaphore`物件。

## <a name="syntax"></a>語法

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>成員

### <a name="public-methods"></a>公用方法

名稱                               | 描述
---------------------------------- | --------------------------------------
[SemaphoreTraits::Unlock](#unlock) | 版本控制共用資源。

## <a name="inheritance-hierarchy"></a>繼承階層

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>需求

**標頭：** corewrappers.h

**命名空間：** Microsoft::WRL::Wrappers::HandleTraits

## <a name="unlock"></a>SemaphoreTraits::Unlock

版本控制共用資源。

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>參數

*h*<br/>
若要處理`Semaphore`物件。

### <a name="remarks"></a>備註

如果在解除鎖定作業不成功，`Unlock()`會發出錯誤，指出失敗的原因。
