---
title: _msize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _msize
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- msize
- _msize
dev_langs:
- C++
helpviewer_keywords:
- memory blocks
- msize function
- _msize function
ms.assetid: 02b1f89e-d0d7-4f12-938a-9eeba48a0f88
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: f669b35ab67ff08835e3335f702027d61581b868
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="msize"></a>_msize
傳回堆積中所配置的記憶體區塊大小。  
  
## <a name="syntax"></a>語法  
  
```  
  
      size_t _msize(  
   void *memblock   
);  
```  
  
#### <a name="parameters"></a>參數  
 `memblock`  
 記憶體區塊的指標。  
  
## <a name="return-value"></a>傳回值  
 `_msize` 傳回不帶正負號的整數大小 (以位元組為單位)。  
  
## <a name="remarks"></a>備註  
 `_msize` 函式會傳回由 `calloc`、`malloc` 或 `realloc` 呼叫所配置的記憶體區塊大小 (以位元組為單位)。  
  
 當應用程式與偵錯版本的 C 執行階段程式庫相連結時，`_msize` 會解析為 [_msize_dbg](../../c-runtime-library/reference/msize-dbg.md)。 如需如何在偵錯程序期間管理堆積的詳細資訊，請參閱 [CRT 偵錯堆積](/visualstudio/debugger/crt-debug-heap-details)。  
  
 這個函式會驗證其參數。 如果 `memblock` 為 null 指標，`_msize` 會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果已處理錯誤，則此函式會將 `errno` 設為 `EINVAL` 並傳回 -1。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_msize`|\<malloc.h>|  
  
 如需相容性的詳細資訊，請參閱＜簡介＞中的[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>程式庫  
 所有版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。  
  
## <a name="example"></a>範例  
 請參閱 [realloc](../../c-runtime-library/reference/realloc.md) 的範例。  
  
## <a name="see-also"></a>另請參閱  
 [記憶體配置](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [_expand](../../c-runtime-library/reference/expand.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)