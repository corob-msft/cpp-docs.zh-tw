---
title: fseek, _lseek 常數
ms.date: 11/04/2016
f1_keywords:
- SEEK_END
- SEEK_SET
- SEEK_CUR
helpviewer_keywords:
- SEEK_SET constant
- SEEK_END constant
- SEEK_CUR constant
ms.assetid: 9deeb13e-5aa3-4c33-80d8-721c80a4de9d
ms.openlocfilehash: a97495aaa5ab0a79ed71a48a12162bd14fc60131
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220448"
---
# <a name="fseek-lseek-constants"></a>fseek, _lseek 常數

## <a name="syntax"></a>語法

```
#include <stdio.h>
```

## <a name="remarks"></a>備註

*origin* 引數會指定初始位置，而且可以是下列所示常數其中之一：

|常數|意義|
|--------------|-------------|
|`SEEK_END`|檔案結尾|
|`SEEK_CUR`|檔案指標的目前位置|
|`SEEK_SET`|檔案開頭|

## <a name="see-also"></a>請參閱

[fseek、_fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)<br/>
[_lseek、_lseeki64](../c-runtime-library/reference/lseek-lseeki64.md)<br/>
[全域常數](../c-runtime-library/global-constants.md)
