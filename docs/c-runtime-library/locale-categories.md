---
title: 地區設定類別
ms.date: 11/04/2016
f1_keywords:
- LC_MAX
- LC_MIN
- LC_MONETARY
- LC_TIME
- LC_NUMERIC
- LC_COLLATE
- LC_CTYPE
- LC_ALL
helpviewer_keywords:
- LC_MIN constant
- LC_MONETARY constant
- LC_CTYPE constant
- locale constants
- LC_MAX constant
- LC_ALL constant
- LC_TIME constant
- LC_NUMERIC constant
- LC_COLLATE constant
ms.assetid: 868f1493-fe5d-4722-acab-bfcd374a063a
ms.openlocfilehash: 841ff5a31bfe9ee5513f76970d3b834f698b92cc
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220188"
---
# <a name="locale-categories"></a>地區設定類別

## <a name="syntax"></a>語法

```
#include <locale.h>
```

## <a name="remarks"></a>備註

地區設定類別為當地語系化常式用來指定要使用之程式地區設定資訊的資訊清單常數。 地區設定指的是位置 (或國家/地區)，您的程式可以針對它對某些方面進行自訂。 與地區設定相關之區域的例子，包括日期格式和貨幣值的顯示格式。

|地區設定類別|部分程式受到影響|
|---------------------|-------------------------------|
|`LC_ALL`|所有與地區設定相關的行為 (所有類別)|
|`LC_COLLATE`|`strcoll` 和 `strxfrm` 函式的行為|
|`LC_CTYPE`|字元處理函式的行為 (`isdigit`、`isxdigit`、`mbstowcs` 及 `mbtowc` 除外，其不受影響)|
|`LC_MAX`|與 `LC_TIME` 相同|
|`LC_MIN`|與 `LC_ALL` 相同|
|`LC_MONETARY`|`localeconv` 函式傳回的貨幣格式資訊|
|`LC_NUMERIC`|針對由 `localeconv` 函式所傳回的格式化輸出常式 (例如 `printf`)、資料轉換常式，以及非貨幣格式資訊的小數點字元|
|`LC_TIME`|`strftime` 函式的行為|

請參閱 [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 以取得範例。

## <a name="see-also"></a>請參閱

[localeconv](../c-runtime-library/reference/localeconv.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[strcoll 函式](../c-runtime-library/strcoll-functions.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[全域常數](../c-runtime-library/global-constants.md)
