---
title: __readdr
ms.date: 11/04/2016
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: 7e6f485eef5e3c54cb406d0c2b3abe824dbf584b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438762"
---
# <a name="readdr"></a>__readdr

讀取指定的偵錯暫存器的值。

## <a name="syntax"></a>語法

```
unsigned         __readdr(unsigned int DebugRegister);
unsigned __int64 __readdr(unsigned int DebugRegister);
```

#### <a name="parameters"></a>參數

*DebugRegister*<br/>
[in]從 0 到 7 可識別偵錯常數暫存器。

## <a name="return-value"></a>傳回值

指定的偵錯暫存器的值。

## <a name="remarks"></a>備註

這些內建函式是只適用於核心模式，而只提供內建函式常式。

## <a name="requirements"></a>需求

|內建|架構|
|---------------|------------------|
|`__readdr`|x86、x64|

**標頭檔** \<intrin.h >

**結束 Microsoft 專屬**

## <a name="see-also"></a>另請參閱

[編譯器內建](../intrinsics/compiler-intrinsics.md)<br/>
[__readeflags](../intrinsics/readeflags.md)