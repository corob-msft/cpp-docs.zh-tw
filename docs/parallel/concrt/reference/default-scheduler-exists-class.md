---
title: default_scheduler_exists 類別
ms.date: 11/04/2016
f1_keywords:
- default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists
- CONCRT/concurrency::default_scheduler_exists::default_scheduler_exists
helpviewer_keywords:
- default_scheduler_exists class
ms.assetid: f6e575e2-4e0f-455a-9e06-54f462ce0c1c
ms.openlocfilehash: 149a220ba9498b1e1c3b7f09cef94c76c34ac4b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501968"
---
# <a name="defaultschedulerexists-class"></a>default_scheduler_exists 類別

這個類別描述預設排程器已經存在於處理序中時呼叫 `Scheduler::SetDefaultSchedulerPolicy` 方法所擲回的例外狀況。

## <a name="syntax"></a>語法

```
class default_scheduler_exists : public std::exception;
```

## <a name="members"></a>成員

### <a name="public-constructors"></a>公用建構函式

|名稱|描述|
|----------|-----------------|
|[default_scheduler_exists](#ctor)|多載。 建構 `default_scheduler_exists` 物件。|

## <a name="inheritance-hierarchy"></a>繼承階層

`exception`

`default_scheduler_exists`

## <a name="requirements"></a>需求

**標頭：** concrt.h

**命名空間：** concurrency

##  <a name="ctor"></a> default_scheduler_exists

建構 `default_scheduler_exists` 物件。

```
explicit _CRTIMP default_scheduler_exists(_In_z_ const char* _Message) throw();

default_scheduler_exists() throw();
```

### <a name="parameters"></a>參數

*訊息 （_m)*<br/>
錯誤的描述性訊息。

## <a name="see-also"></a>另請參閱

[concurrency 命名空間](concurrency-namespace.md)
