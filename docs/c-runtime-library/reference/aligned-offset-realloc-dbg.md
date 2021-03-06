---
title: _aligned_offset_realloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_offset_realloc_dbg
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
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
ms.openlocfilehash: 7684a752f489eb726b2105b1055b6da1e86e9cd1
ms.sourcegitcommit: beeb77b2976e997debc55b1af35024cc62e62799
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/06/2018
ms.locfileid: "52977819"
---
# <a name="alignedoffsetreallocdbg"></a>_aligned_offset_realloc_dbg

變更使用 [_aligned_malloc](aligned-malloc.md) 或 [_aligned_offset_malloc](aligned-offset-malloc.md) 所配置的記憶體區塊大小 (僅限偵錯版本)。

## <a name="syntax"></a>語法

```C
void * _aligned_offset_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>參數

*memblock*<br/>
目前記憶體區塊指標。

*size*<br/>
記憶體配置的大小。

*對齊方式*<br/>
對齊值，必須是 2 的整數冪。

*offset*<br/>
記憶體配置中要強制對齊的位移。

*filename*<br/>
要求的原始程式檔的名稱指標**aligned_offset_realloc**作業或**NULL**。

*linenumber*<br/>
原始程式檔中的行號所在**aligned_offset_realloc**要求作業，或**NULL**。

## <a name="return-value"></a>傳回值

**_aligned_offset_realloc_dbg**傳回重新配置後 （且可能有移動） 記憶體區塊的 void 指標。 傳回值是**NULL**如果大小為零，而且緩衝區引數不是**NULL**，或如果沒有足夠的可用記憶體將區塊展開指定的大小。 在第一種情況中，會釋放原始區塊。 在第二種情況中，原始區塊會保留不變。 儲存空間的傳回值指標，是能夠適當地對齊任何物件類型之儲存區的保證。 若要取得 Void 類型以外的指標，請對傳回值使用類型轉換。

## <a name="remarks"></a>備註

**_aligned_offset_realloc_dbg**是偵錯版本[_aligned_offset_realloc](aligned-offset-realloc.md)函式。 當[_DEBUG](../../c-runtime-library/debug.md)未定義，每次呼叫 **_aligned_offset_realloc_dbg**的呼叫會降低 **_aligned_offset_realloc**。 兩者 **_aligned_offset_realloc**並 **_aligned_offset_realloc_dbg**重新配置基底堆積中的記憶體區塊，但 **_aligned_offset_realloc_dbg**容納數個偵錯功能： 以測試遺漏，區塊使用者部分任一端使用緩衝區和*檔名*/*linenumber*資訊來判斷的原點配置要求。 追蹤特定配置類型的區塊類型參數不是支援的偵錯功能的對齊的配置。 對齊的配置會顯示為 _NORMAL_BLOCK 區塊型別。

像是[_aligned_offset_malloc](aligned-offset-malloc.md)， **_aligned_offset_realloc_dbg**可讓結構對齊結構中的位移。

**_realloc_dbg**重新配置比要求稍微多一些的空間與指定的記憶體區塊*newSize*。 *newSize*可能大於或小於原本配置的記憶體區塊的大小。 偵錯堆積管理員會使用額外的空間連結偵錯記憶體區塊，以及為應用程式提供偵錯標頭資訊和覆寫緩衝區。 重新配置可能會導致將原始記憶體區塊移到堆積中的不同位置，也可能會變更記憶體區塊的大小。 若記憶體區塊已移動，則會覆寫原始區塊的內容。

此函式會將**errno**要**ENOMEM**如果記憶體配置失敗，或者要求的大小大於 **_HEAP_MAXREQ**。 如需詳細資訊**errno**，請參閱[errno、 _doserrno、 _sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。 此外， **_aligned_offset_realloc_dbg**會驗證其參數。 如果*對齊*不是 2 的冪，或如果*位移*大於或等於*大小*和非零值，這個函式會叫用無效參數處理常式中所述[參數驗證](../../c-runtime-library/parameter-validation.md)。 如果允許繼續執行，則此函數會傳回**NULL**並設定**errno**來**EINVAL**。

如需在偵錯版之基底堆積中如何配置、初始化及管理記憶體區塊的資訊，請參閱 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)。 如需配置區塊類型以及如何使用它們的資訊，請參閱[偵錯堆積上的區塊類型](/visualstudio/debugger/crt-debug-heap-details)。 如需在應用程式的偵錯組建中呼叫標準堆積函式以及其偵錯版本之間的差異的資訊，請參閱[堆積配置函式的偵錯版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)。

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**_aligned_offset_realloc_dbg**|\<crtdbg.h>|

如需相容性的詳細資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>程式庫

僅限偵錯版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。

## <a name="see-also"></a>另請參閱

[偵錯常式](../../c-runtime-library/debug-routines.md)<br/>
