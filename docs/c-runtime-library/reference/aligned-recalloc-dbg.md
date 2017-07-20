---
title: _aligned_recalloc_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _aligned_recalloc_dbg
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
apitype: DLLExport
f1_keywords:
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
caps.latest.revision: 7
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
ms.openlocfilehash: 492df3def134d16106c90a60c4c4c0c68227be09
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="alignedrecallocdbg"></a>_aligned_recalloc_dbg
變更使用 [_aligned_malloc](../../c-runtime-library/reference/aligned-malloc.md) 或 [_aligned_offset_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md) 所配置的記憶體區塊大小，並將記憶體初始化為 0 (僅限偵錯版本)。  
  
## <a name="syntax"></a>語法  
  
```  
void * _aligned_recalloc_dbg(  
   void * memblock,   
   size_t num,  
   size_t size,   
   size_t alignment,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### <a name="parameters"></a>參數  
 [in] `memblock`  
 目前記憶體區塊指標。  
  
 [in] `num`  
 項目的數目。  
  
 [in] `size`  
 每個項目的大小 (位元組)。  
  
 [in] `alignment`  
 對齊值，必須是 2 的整數冪。  
  
 [in] `filename`  
 要求配置作業之原始程式檔的名稱的指標，或為 `NULL`。  
  
 [in] `linenumber`  
 原始程式檔中的行號，其中要求配置作業，或為 `NULL`。  
  
## <a name="return-value"></a>傳回值  
 `_aligned_recalloc_dbg` 會傳回重新配置後 (且可能有移動) 記憶體區塊的 Void 指標。 若大小為 0，且緩衝區引數不是 `NULL`，則傳回值為 `NULL`，或者，若沒有足夠的可用記憶體將區塊展開為指定大小，傳回值也會是 NULL。 在第一種情況中，會釋放原始區塊。 在第二種情況中，原始區塊會保留不變。 儲存空間的傳回值指標，是能夠適當地對齊任何物件類型之儲存區的保證。 若要取得 Void 類型以外的指標，請對傳回值使用類型轉換。  
  
 重新配置記憶體並變更區塊的對齊是不對的。  
  
## <a name="remarks"></a>備註  
 `_aligned_recalloc_dbg` 是 [_aligned_recalloc](../../c-runtime-library/reference/aligned-recalloc.md) 函式的偵錯版本。 當 [_DEBUG](../../c-runtime-library/debug.md) 未定義時，每個 `_aligned_recalloc_dbg` 的呼叫會降至 `_aligned_recalloc` 的呼叫。 `_aligned_recalloc` 和 `_aligned_recalloc_dbg` 都會重新配置基底堆積中的記憶體區塊，但 `_aligned_recalloc_dbg` 還容納數種偵錯功能：在區塊的使用者部分的任一端使用緩衝區以測試遺漏，以及追蹤特定配置類型的區塊類型參數，還有判斷配置要求來源的 `filename`/`linenumber` 資訊。  
  
 `_aligned_recalloc_dbg` 會使用比要求的大小還要稍微多一些的空間重新配置指定的記憶體區塊 (`num` * `size`)，而要求的大小可能會比原始配置的記憶體區塊大小更大或更小。 偵錯堆積管理員會使用額外的空間連結偵錯記憶體區塊，以及為應用程式提供偵錯標頭資訊和覆寫緩衝區。 重新配置可能會導致將原始記憶體區塊移到堆積中的不同位置，也可能會變更記憶體區塊的大小。 區塊的使用者部分會填入值 0xCD，且覆寫緩衝區會填入 0xFD。  
  
 若記憶體配置失敗，`_aligned_recalloc_dbg` 會將 `errno` 設定為 `ENOMEM`；若所需的記憶體數量 (包含之前提到的額外負荷) 超過 `EINVAL`，則會傳回 `_HEAP_MAXREQ`。 如需此錯誤碼和其他錯誤碼的資訊，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
 此外，`_aligned_recalloc_dbg` 也會驗證其參數。 如果 `alignment` 不是 2 的乘冪，則此函式會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 若允許繼續執行，此函式會傳回 `NULL`，並將 `errno` 設為 `EINVAL`。  
  
 如需在偵錯版本的基底堆積中如何配置、初始化及管理記憶體區塊的資訊，請參閱 [CRT 偵錯堆積詳細資料](/visualstudio/debugger/crt-debug-heap-details)。 如需配置區塊類型以及如何使用它們的資訊，請參閱[偵錯堆積上的區塊類型](/visualstudio/debugger/crt-debug-heap-details)。 如需在應用程式的偵錯組建中呼叫標準堆積函式以及其偵錯版本之間的差異的資訊，請參閱[堆積配置函式的偵錯版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_aligned_recalloc_dbg`|\<crtdbg.h>|  
  
 如需相容性的詳細資訊，請參閱＜簡介＞中的[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>程式庫  
 僅限偵錯版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯常式](../../c-runtime-library/debug-routines.md)