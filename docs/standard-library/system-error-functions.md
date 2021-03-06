---
title: '&lt;system_error&gt; 函式'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::generic_category
- system_error/std::make_error_code
- system_error/std::make_error_condition
- system_error/std::system_category
ms.assetid: 57d6f15f-f0b7-4e2f-80fe-31d3c320ee33
helpviewer_keywords:
- std::generic_category
- std::make_error_code
- std::make_error_condition
- std::system_category
ms.openlocfilehash: 24890830456e3c1026b02960aa650a43da3b6067
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50554370"
---
# <a name="ltsystemerrorgt-functions"></a>&lt;system_error&gt; 函式

||||
|-|-|-|
|[generic_category](#generic_category)|[make_error_code](#make_error_code)|[make_error_condition](#make_error_condition)|
|[system_category](#system_category)|

## <a name="generic_category"></a>  generic_category

代表泛型錯誤的分類。

```cpp
extern const error_category& generic_category();
```

### <a name="remarks"></a>備註

`generic_category`物件會實作[error_category](../standard-library/error-category-class.md)。

## <a name="make_error_code"></a>  make_error_code

建立錯誤碼物件。

```cpp
error_code make_error_code(generic_errno _Errno);
```

### <a name="parameters"></a>參數

|參數|描述|
|---------------|-----------------|
|*_Errno*|要儲存於錯誤碼物件中的列舉值。|

### <a name="return-value"></a>傳回值

錯誤碼物件。

### <a name="remarks"></a>備註

## <a name="make_error_condition"></a>  make_error_condition

建立錯誤條件物件。

```cpp
error_condition make_error_condition(generic_errno _Errno);
```

### <a name="parameters"></a>參數

|參數|描述|
|---------------|-----------------|
|*_Errno*|要儲存於錯誤條件物件中的列舉值。|

### <a name="return-value"></a>傳回值

錯誤條件物件。

### <a name="remarks"></a>備註

## <a name="system_category"></a>  system_category

代表低階系統溢位所造成的錯誤分類。

```cpp
extern const error_category& system_category();
```

### <a name="remarks"></a>備註

`system_category`物件會實作[error_category](../standard-library/error-category-class.md)。

## <a name="see-also"></a>另請參閱

[<system_error>](../standard-library/system-error.md)<br/>
