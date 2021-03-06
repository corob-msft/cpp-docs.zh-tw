---
title: Microsoft::WRL::Wrappers::HandleTraits Namespace
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 55e1dfea2d4075a5a37b9654a70e9ce74383ea53
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335730"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits Namespace

描述常見的控制代碼為基礎的資源類型的特性。

## <a name="syntax"></a>語法

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>成員

### <a name="structures"></a>結構

|名稱|描述|
|----------|-----------------|
|[CriticalSectionTraits 結構](criticalsectiontraits-structure.md)|特製化`CriticalSection`支援無效的重要區段或函式來釋放重要區段物件。|
|[EventTraits 結構](eventtraits-structure.md)|定義特性`Event`類別控制代碼。|
|[FileHandleTraits 結構](filehandletraits-structure.md)|定義的檔案控制代碼的特性。|
|[HANDLENullTraits 結構](handlenulltraits-structure.md)|定義未初始化的控制代碼的一般特性。|
|[HANDLETraits 結構](handletraits-structure.md)|定義通用的控制代碼的特性。|
|[MutexTraits 結構](mutextraits-structure.md)|定義通用特性[Mutex](mutex-class.md)類別。|
|[SemaphoreTraits 結構](semaphoretraits-structure.md)|定義號誌物件的一般的特性。|
|[SRWLockExclusiveTraits 結構](srwlockexclusivetraits-structure.md)|描述一般特性`SRWLock`獨佔的鎖定模式的類別。|
|[SRWLockSharedTraits 結構](srwlocksharedtraits-structure.md)|描述一般特性`SRWLock`以共用鎖定模式的類別。|

## <a name="requirements"></a>需求

**標頭：** corewrappers.h

**命名空間：** Microsoft::WRL::Wrappers

## <a name="see-also"></a>另請參閱

[Microsoft::WRL::Wrappers 命名空間](microsoft-wrl-wrappers-namespace.md)