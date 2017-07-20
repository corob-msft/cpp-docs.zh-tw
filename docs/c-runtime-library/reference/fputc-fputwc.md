---
title: "fputc、fputwc | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fputc
- fputwc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fputc
- fputwc
- _fputtc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 7eb1bb55bd153f4ef5387b616b72f611e3a50a9f
ms.contentlocale: zh-tw
ms.lasthandoff: 04/04/2017

---
# <a name="fputc-fputwc"></a>fputc、fputwc
將一個字元寫入資料流。  
  
## <a name="syntax"></a>語法  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>參數  
 `c`  
 待寫入字元。  
  
 `stream`  
 `FILE` 結構的指標。  
  
## <a name="return-value"></a>傳回值  
 所有這些函式都會傳回寫入的字元。 針對 `fputc`，傳回值 `EOF` 表示錯誤。 針對 `fputwc`，傳回值 `WEOF` 表示錯誤。 如果 `stream` 為 `NULL`，則這些函式會叫用無效的參數處理常式 (如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述)。 如果允許繼續執行，這些函式會傳回 `EOF`，並將 `errno` 設為 `EINVAL`。  
  
 如需這些錯誤碼和其他錯誤碼的詳細資訊，請參閱 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>備註  
 所有這些函式都會將單一字元 `c` 寫入至檔案中相關聯檔案位置指標 (定義時) 所指出的位置，並適當地往前移動指標。 如果是`fputc`和`fputwc`，與檔案關聯`stream`。 如果檔案不支援定位要求，或以附加模式予以開啟，則會將字元附加至資料流結尾。  
  
 如果資料流是以 ANSI 模式開啟，則這兩個函式的行為相同。 `fputc` 目前不支援輸出至 UNICODE 資料流。  
  
 具有 `_nolock` 尾碼的版本完全一致，不同之處在於不受保護，不能免於其他執行緒的干擾。 如需詳細資訊，請參閱 [_fputc_nolock、_fputwc_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md)。  
  
 常式特定備註如下。  
  
|常式|備註|  
|-------------|-------------|  
|`fputc`|相當於 `putc`，但僅實作為函式，而不是函式和巨集。|  
|`fputwc`|`fputc` 的寬字元版本。 根據以文字模式還是二進位模式開啟 `stream`，將 `c` 寫入為多位元組字元或寬字元。|  
  
### <a name="generic-text-routine-mappings"></a>一般文字常式對應  
  
|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## <a name="requirements"></a>需求  
  
|函式|必要的標頭|  
|--------------|---------------------|  
|`fputc`|\<stdio.h>|  
|`fputwc`|\<stdio.h> 或 \<wchar.h>|  
  
 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 應用程式不支援主控台。 與主控台 (`stdin`、`stdout` 和 `stderr`) 關聯的標準資料流控制代碼必須重新導向，之後 C 執行階段函式才能在 [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] 應用程式中使用它們。 如需相容性的詳細資訊，請參閱[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>範例  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
```Output  
This is a test of fputc!!  
```  
  
## <a name="see-also"></a>另請參閱  
 [資料流 I/O](../../c-runtime-library/stream-i-o.md)   
 [fgetc、fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc、putwc](../../c-runtime-library/reference/putc-putwc.md)