---
title: '運算子&lt;運算子 (microsoft:: wrl)'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::operator<
ms.assetid: bfae0e1c-1648-482b-99c2-3217d62aba46
ms.openlocfilehash: 8b9d9936eabb75b58eabde487db8d1eb42abc9dd
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335697"
---
# <a name="operatorlt-operator-microsoftwrl"></a>運算子&lt;運算子 (microsoft:: wrl)

判斷一個物件的位址是否小於另一個。

## <a name="syntax"></a>語法

```cpp
template<class T, class U>
bool operator<(const ComPtr<T>& a, const ComPtr<U>& b) throw();
template<class T, class U>
bool operator<(const Details::ComPtrRef<ComPtr<T>>& a, const Details::ComPtrRef<ComPtr<U>>& b) throw();
```

### <a name="parameters"></a>參數

*a*<br/>
左物件。

*b*<br/>
右物件。

## <a name="return-value"></a>傳回值

**true**如果的地址小於的位址*b*; 否則**false**。

## <a name="requirements"></a>需求

**標頭：** client.h

**命名空間：** Microsoft:: wrl

## <a name="see-also"></a>另請參閱

[Microsoft::WRL 命名空間](microsoft-wrl-namespace.md)