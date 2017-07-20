---
title: "vprintf、_vprintf_l、vwprintf、_vwprintf_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- vprintf
- _vwprintf_l
- _vprintf_l
- vwprintf
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
- vwprintf
- _vtprintf
dev_langs:
- C++
helpviewer_keywords:
- vwprintf function
- _vwprintf_l function
- vwprintf_l function
- _vtprintf function
- vtprintf_l function
- vprintf function
- _vprintf_l function
- vprintf_l function
- vtprintf function
- _vtprintf_l function
- formatted text [C++]
ms.assetid: 44549505-00a0-4fa7-9a85-f2e666f55a38
caps.latest.revision: 20
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
ms.openlocfilehash: bcb54b081d77f6a7346a48680d56850eda7eb630
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="vprintf-vprintfl-vwprintf-vwprintfl"></a>vprintf、_vprintf_l、vwprintf、_vwprintf_l
使用引數清單的指標，撰寫格式化的輸出。 這些函式已有更安全的版本，請參閱 [vprintf_s、_vprintf_s_l、vwprintf_s、_vwprintf_s_l](../../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)。  
  
## <a name="syntax"></a>語法  
  
```  
int vprintf(  
   const char *format,  
   va_list argptr   
);  
int _vprintf_l(  
   const char *format,  
   locale_t locale,  
   va_list argptr   
);  
int vwprintf(  
   const wchar_t *format,  
   va_list argptr   
);  
int _vwprintf_l(  
   const wchar_t *format,  
   locale_t locale,  
   va_list argptr   
);  
```  
  
#### <a name="parameters"></a>參數  
 `format`  
 格式規格。  
  
 `argptr`  
 引數清單的指標。  
  
 `locale`  
 要使用的地區設定。  
  
 如需詳細資訊，請參閱[格式規格](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)。  
  
## <a name="return-value"></a>傳回值  
 `vprintf` 和 `vwprintf` 會傳回寫入的字元數，但不包含終止 Null 字元，或在發生輸出錯誤時傳回負值。 如果 `format` 為 Null 指標，或者此格式字串包含無效格式化字元，則會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 若允許繼續執行，函式會傳回 -1，並將 `errno` 設為 `EINVAL`。  
  
 如需這些錯誤碼和其他錯誤碼的資訊，請參閱 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>備註  
 所有這些函式都會接受引數清單的指標，然後格式化指定的資料，並將其寫入 `stdout`。  
  
 `vwprintf` 是 `vprintf` 的寬字元版本；如果資料流是以 ANSI 模式開啟，則這兩個函式的行為相同。 `vprintf` 目前不支援輸出至 UNICODE 資料流。  
  
 這些有 `_l` 尾碼的函式版本是一樣的，不同之處在於會使用傳入的地區設定，而不使用目前的執行緒地區設定。  
  
> [!IMPORTANT]
>  確認 `format` 不是使用者定義的字串。 如需詳細資訊，請參閱 [Avoiding Buffer Overruns (避免緩衝區滿溢)](http://msdn.microsoft.com/library/windows/desktop/ms717795)。 請注意，偵測到無效的格式字串並產生錯誤。  
  
### <a name="generic-text-routine-mappings"></a>一般文字常式對應  
  
|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_vtprintf`|`vprintf`|`vprintf`|`vwprintf`|  
|`_vtprintf_l`|`_vprintf_l`|`_vprintf_l`|`_vwprintf_l`|  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|選擇性標頭|  
|-------------|---------------------|----------------------|  
|`vprintf`, `_vprintf_l`|\<stdio.h> 和 \<stdarg.h>|\<varargs.h>*|  
|`vwprintf`, `_vwprintf_l`|\<stdio.h> 或 \<wchar.h>，以及 \<stdarg.h>|\<varargs.h>*|  
  
 \* UNIX V 相容性的必要項。  
  
 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 應用程式不支援主控台。 與主控台 (`stdin`、`stdout` 和 `stderr`) 關聯的標準資料流控制代碼必須重新導向，之後 C 執行階段函式才能在 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 應用程式中使用它們。 如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另請參閱  
 [資料流 I/O](../../c-runtime-library/stream-i-o.md)   
 [vprintf 函式](../../c-runtime-library/vprintf-functions.md)   
 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [printf、_printf_l、wprintf、_wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [va_arg、va_copy、va_end、va_start](../../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md)