---
title: _getdcwd_dbg、_wgetdcwd_dbg
ms.date: 11/04/2016
apiname:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
ms.openlocfilehash: 700cfe732dc390ca59a976694403bb3d91af5980
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547169"
---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg、_wgetdcwd_dbg

偵錯版本的 [_getdcwd、_wgetdcwd](getdcwd-wgetdcwd.md) 函式 (僅於偵錯期間可供使用)。

## <a name="syntax"></a>語法

```C
char *_getdcwd_dbg(
   int drive,
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetdcwd_dbg(
   int drive,
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>參數

*磁碟機*<br/>
磁碟機的名稱。

*buffer*<br/>
路徑的儲存位置。

*maxlen*<br/>
路徑以字元為單位的最大長度： **char**如 **_getdcwd_dbg**並**wchar_t**如 **_wgetdcwd_dbg**。

*blockType*<br/>
要求的記憶體區塊類型： **_CLIENT_BLOCK**或是 **_NORMAL_BLOCK**。

*filename*<br/>
要求配置作業之原始程式檔名稱的指標或**NULL**。

*linenumber*<br/>
其中要求配置作業，原始程式檔中的行號或**NULL**。

## <a name="return-value"></a>傳回值

將指標傳回至*緩衝區*。 A **NULL**傳回值表示錯誤，並**errno**設為**ENOMEM**，表示記憶體不足，無法配置*maxlen*位元組 (當**NULL**引數指定為*緩衝區*)，或**ERANGE**，表示路徑長度超過*maxlen*字元。 如需詳細資訊，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="remarks"></a>備註

**_Getdcwd_dbg**並 **_wgetdcwd_dbg**函式 **_getdcwd**並 **_wgetdcwd**不同之處在於，當 **_DEBUG**是定義，這些函式使用的偵錯版本**malloc**並 **_malloc_dbg**來配置記憶體**NULL**傳遞作為*緩衝區*參數。 如需詳細資訊，請參閱 [_malloc_dbg](malloc-dbg.md)。

在大多數情況中，您不需要明確地呼叫這些函式。 相反地，您可以定義 **_CRTDBG_MAP_ALLOC**旗標。 當 **_CRTDBG_MAP_ALLOC**定義，呼叫 **_getdcwd**並 **_wgetdcwd**重新對應至 **_getdcwd_dbg**和 **_wgetdcwd_dbg**分別與*blockType*設定為 **_NORMAL_BLOCK**。 因此，您不需要明確呼叫這些函式，除非您想要將標示為堆積區塊 **_CLIENT_BLOCK**。 如需詳細資訊，請參閱[偵錯堆積上的區塊類型](/visualstudio/debugger/crt-debug-heap-details)。

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|Tchar.h 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|
|-------------|---------------------|
|**_getdcwd_dbg**|\<crtdbg.h>|
|**_wgetdcwd_dbg**|\<crtdbg.h>|

如需相容性的詳細資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[_getdcwd、_wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[目錄控制](../../c-runtime-library/directory-control.md)<br/>
[堆積配置函式的偵錯版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
