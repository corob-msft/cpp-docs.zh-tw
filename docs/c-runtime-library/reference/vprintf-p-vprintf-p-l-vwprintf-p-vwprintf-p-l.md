---
title: _vprintf_p、_vprintf_p_l、_vwprintf_p、_vwprintf_p_l
ms.date: 11/04/2016
apiname:
- _vwprintf_p
- _vprintf_p
- _vprintf_p_l
- _vwprintf_p_l
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
- _vwprintf_p_l
- vprintf_p
- _vprintf_p_l
- _vwprintf_p
- vprintf_p_l
- vwprintf_p_l
- vwprintf_p
- vtprintf_p
- _vtprintf_p
- _vprintf_p
helpviewer_keywords:
- _vtprintf_p_l function
- _vtprintf_p function
- vtprintf_p function
- _vwprintf_p function
- _vwprintf_p_l function
- _vprintf_p function
- _vprintf_p_l function
- vprintf_p_l function
- vwprintf_p function
- vprintf_p function
- vtprintf_p_l function
- vwprintf_p_l function
- formatted text [C++]
ms.assetid: 3f99bde3-c891-493d-908f-30559c421058
ms.openlocfilehash: 266df8c033fc9d1c8459aff9f2b95771947d88d1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635080"
---
# <a name="vprintfp-vprintfpl-vwprintfp-vwprintfpl"></a>_vprintf_p、_vprintf_p_l、_vwprintf_p、_vwprintf_p_l

使用引數清單的指標撰寫格式化的輸出，並啟用引數使用的順序規格。

## <a name="syntax"></a>語法

```C
int _vprintf_p(
   const char *format,
   va_list argptr
);
int _vprintf_p_l(
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vwprintf_p(
   const wchar_t *format,
   va_list argptr
);
int _vwprintf_p_l(
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>參數

*格式*<br/>
格式規格。

*argptr*<br/>
引數清單的指標。

*locale*<br/>
要使用的地區設定。

如需詳細資訊，請參閱 [格式規格](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)。

## <a name="return-value"></a>傳回值

**_vprintf_p**並 **_vwprintf_p**傳回寫入的字元數，如果發生輸出錯誤，不包括結束的 null 字元或為負值。

## <a name="remarks"></a>備註

所有這些函式都會接受引數清單的指標，然後格式化並寫入至指定的資料**stdout**。 這些函式與差異**vprintf_s**並**vwprintf_s**僅在於它們支援讓您指定在其中使用的引數的順序。 如需詳細資訊，請參閱 [printf_p 位置參數](../../c-runtime-library/printf-p-positional-parameters.md)。

**_vwprintf_p**是寬字元版本 **_vprintf_p**; 如果資料流以 ANSI 模式開啟兩個函式行為相同。 **_vprintf_p**目前不支援輸出至 UNICODE 資料流。

使用這些函式的版本 **_l**尾碼都相同，只不過它們而不是目前執行緒的地區設定傳入的地區設定參數。

> [!IMPORTANT]
> 確認 *format* 不是使用者定義的字串。 如需詳細資訊，請參閱 [Avoiding Buffer Overruns (避免緩衝區滿溢)](/windows/desktop/SecBP/avoiding-buffer-overruns)。

如果*格式*為 null 指標，或如果格式字串包含無效格式化字元，無效參數處理常式會叫用，如中所述[參數驗證](../../c-runtime-library/parameter-validation.md)。 如果允許繼續執行，函式會傳回-1，並設定**errno**要**EINVAL**。

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtprintf_p**|**_vprintf_p**|**_vprintf_p**|**_vwprintf_p**|
|**_vtprintf_p_l**|**_vprintf_p_l**|**_vprintf_p_l**|**_vwprintf_p_l**|

## <a name="requirements"></a>需求

|常式傳回的值|必要的標頭|選擇性標頭|
|-------------|---------------------|----------------------|
|**_vprintf_p**， **_vprintf_p_l**|\<stdio.h> 和 \<stdarg.h>|\<varargs.h>*|
|**_vwprintf_p**， **_vwprintf_p_l**|\<stdio.h> 或 \<wchar.h>，以及 \<stdarg.h>|\<varargs.h>*|

\* UNIX V 相容性的必要項目。

通用 Windows 平台 (UWP) 應用程式中不支援主控台。 主控台中，相關聯的標準資料流控制代碼**stdin**， **stdout**，並**stderr**，必須重新導向，C 執行階段函式才能使用它們在 UWP 應用程式. 如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[資料流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf 函式](../../c-runtime-library/vprintf-functions.md)<br/>
[_fprintf_p、_fprintf_p_l、_fwprintf_p、_fwprintf_p_l](fprintf-p-fprintf-p-l-fwprintf-p-fwprintf-p-l.md)<br/>
[_printf_p、_printf_p_l、_wprintf_p、_wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[_sprintf_p、_sprintf_p_l、_swprintf_p、_swprintf_p_l](sprintf-p-sprintf-p-l-swprintf-p-swprintf-p-l.md)<br/>
[vsprintf_s、_vsprintf_s_l、vswprintf_s、_vswprintf_s_l](vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)<br/>
[va_arg、va_copy、va_end、va_start](va-arg-va-copy-va-end-va-start.md)<br/>
[_vfprintf_p、_vfprintf_p_l、_vfwprintf_p、_vfwprintf_p_l](vfprintf-p-vfprintf-p-l-vfwprintf-p-vfwprintf-p-l.md)<br/>
[_printf_p、_printf_p_l、_wprintf_p、_wprintf_p_l](printf-p-printf-p-l-wprintf-p-wprintf-p-l.md)<br/>
[printf_p 位置參數](../../c-runtime-library/printf-p-positional-parameters.md)<br/>
