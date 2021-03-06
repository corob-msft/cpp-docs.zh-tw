---
title: CreateClassFactory 函式
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateClassFactory
helpviewer_keywords:
- CreateClassFactory function
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
ms.openlocfilehash: e7e213d1b0679f17ce070de85ee9410ff9546716
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336145"
---
# <a name="createclassfactory-function"></a>CreateClassFactory 函式

建立會產生指定類別之執行個體的處理站。

## <a name="syntax"></a>語法

```cpp
template<typename Factory>
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(
   _In_ unsigned int *flags,
   _In_ const CreatorMap* entry,
   REFIID riid,
   _Outptr_ IUnknown **ppFactory
) throw();
```

### <a name="parameters"></a>參數

*flags*<br/>
一或多個組合[RuntimeClassType](runtimeclasstype-enumeration.md)列舉值。

*entry*<br/>
指標[CreatorMap](creatormap-structure.md) ，其中包含參數的初始設定和註冊資訊*riid*。

*riid*<br/>
參考介面識別碼。

*ppFactory*<br/>
如果這項作業成功完成，class factory 的指標。

## <a name="return-value"></a>傳回值

如果作業成功，會傳送 S_OK；反之則傳送表示錯誤的 HRESULT 值。

## <a name="remarks"></a>備註

如果，就會發出判斷提示錯誤範本參數*Factory*不是衍生自介面`IClassFactory`。

## <a name="requirements"></a>需求

**標頭：** module.h

**命名空間：** Microsoft:: wrl

## <a name="see-also"></a>另請參閱

[Microsoft::WRL::Wrappers::Details 命名空間](microsoft-wrl-wrappers-details-namespace.md)