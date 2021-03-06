---
title: '&lt;thread&gt;'
ms.date: 11/04/2016
f1_keywords:
- <thread>
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
ms.openlocfilehash: 43fb79ceda6de7409e6f93797ce2f4ff213c43ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487512"
---
# <a name="ltthreadgt"></a>&lt;thread&gt;

包含標準標頭\<執行緒 > 來定義類別**執行緒**和各種支援的函式。

## <a name="syntax"></a>語法

```cpp
#include <thread>
```

## <a name="remarks"></a>備註

> [!NOTE]
> 在編譯使用的程式碼 **/clr**，此標頭會遭到封鎖。

`__STDCPP_THREADS__`巨集定義為非零值，表示執行緒會受到此標頭。

## <a name="members"></a>成員

### <a name="public-classes"></a>公用類別

|名稱|描述|
|----------|-----------------|
|[thread 類別](../standard-library/thread-class.md)|定義用來觀察和管理應用程式中執行的執行緒的物件。|

### <a name="public-structures"></a>公用結構

|名稱|描述|
|----------|-----------------|
|[hash 結構 (C++ 標準程式庫)](../standard-library/hash-structure-stl.md)|定義成員函式的傳回值，這個值是唯一決定`thread::id`。 此成員函式定義[雜湊](../standard-library/hash-class.md)適用於類型的對應值的函式`thread::id`到索引值的分佈。|

### <a name="public-functions"></a>公用函式

|名稱|描述|
|----------|-----------------|
|[get_id](../standard-library/thread-functions.md#get_id)|可唯一識別執行目前的執行緒。|
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|封鎖呼叫執行緒。|
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|封鎖呼叫執行緒，至少直到指定的時間。|
|[swap](../standard-library/thread-functions.md#swap)|交換兩個狀態**執行緒**物件。|
|[yield](../standard-library/thread-functions.md#yield)|向作業系統表示執行其他執行緒，即使目前的執行緒通常會繼續執行。|

### <a name="public-operators"></a>公用運算子

|名稱|描述|
|----------|-----------------|
|[運算子 > = 運算子](../standard-library/thread-operators.md#op_gt_eq)|判斷某個 `thread::id` 物件是否大於或等於另一個。|
|[運算子 > 運算子](../standard-library/thread-operators.md#op_gt)|判斷某個 `thread::id` 物件是否大於另一個。|
|[運算子 < = 運算子](../standard-library/thread-operators.md#op_lt_eq)|判斷某個 `thread::id` 物件是否小於或等於另一個。|
|[運算子 < 運算子](../standard-library/thread-operators.md#op_lt)|判斷某個 `thread::id` 物件是否小於另一個。|
|[運算子 ！ = 運算子](../standard-library/thread-operators.md#op_neq)|比較兩個 `thread::id` 物件是否不相等。|
|[運算子 = = 運算子](../standard-library/thread-operators.md#op_eq_eq)|比較兩個 `thread::id` 物件是否相等。|
|[運算子 << 運算子](../standard-library/thread-operators.md#op_lt_lt)|將 `thread::id` 物件的文字表示插入資料流。|

## <a name="see-also"></a>另請參閱

[標頭檔參考](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
