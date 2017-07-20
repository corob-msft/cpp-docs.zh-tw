---
title: "_strncoll、_wcsncoll、_mbsncoll、_strncoll_l、_wcsncoll_l、_mbsncoll_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _strncoll
- _mbsncoll_l
- _wcsncoll
- _wcsncoll_l
- _mbsncoll
- _strncoll_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbsncoll_l
- strncoll
- _wcsncoll
- _tcsnccoll
- _ftcsnccoll
- wcsncoll
- _mbsncoll
- wcsncoll_l
- strncoll_l
- _ftcsncoll
- _strncoll
- _tcsncoll
- mbsncoll
dev_langs:
- C++
helpviewer_keywords:
- _strncoll_l function
- code pages, using for string comparisons
- _strncoll function
- _mbsncoll function
- ftcsncoll function
- strncoll function
- _ftcsncoll function
- strncoll_l function
- wcsncoll function
- mbsncoll function
- _tcsncoll function
- _tcsnccoll function
- wcsncoll_l function
- tcsnccoll function
- mbsncoll_l function
- _mbsncoll_l function
- tcsncoll function
- _wcsncoll function
- strings [C++], comparing by code page
- _ftcsnccoll function
- ftcsnccoll function
- _wcsncoll_l function
ms.assetid: e659a5a4-8afe-4033-8e72-17ffd4bdd8e9
caps.latest.revision: 21
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
ms.openlocfilehash: d9498ca8aaab36e7443488a1c98b70ad4b7604d5
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="strncoll-wcsncoll-mbsncoll-strncolll-wcsncolll-mbsncolll"></a>_strncoll、_wcsncoll、_mbsncoll、_strncoll_l、_wcsncoll_l、_mbsncoll_l
使用地區設定特定資訊，以比較字串。  
  
> [!IMPORTANT]
> 不可在於  `_mbsncoll` 中執行的應用程式中使用 `_mbsncoll_l` 和 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]。 如需詳細資訊，請參閱 [/ZW 不支援 CRT 函式](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## <a name="syntax"></a>語法  
  
```  
int _strncoll(  
   const char *string1,  
   const char *string2,  
   size_t count   
);  
int _wcsncoll(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count   
);  
int _mbsncoll(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count   
);  
int _strncoll_l(  
   const char *string1,  
   const char *string2,  
   size_t count,  
   _locale_t locale  
);  
int _wcsncoll_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   size_t count,  
   _locale_t locale  
);  
int _mbsncoll_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>參數  
 `string1, string2`  
 以 Null 結束的待比較字串。  
  
 `count`  
 要比較的字元數。  
  
 `locale`  
 要使用的地區設定。  
  
## <a name="return-value"></a>傳回值  
 所有這些函式都會傳回值，而值表示 `string1` 子字串和 `string2` 子字串的關聯性，如下所示。  
  
|傳回值|string1 與 string2 的關係|  
|------------------|----------------------------------------|  
|< 0|`string1` 小於 `string2`。|  
|0|`string1` 等同於 `string2`|  
|> 0|`string1` 大於 `string2`。|  
  
 所有這些函式都會傳回 `_NLSCMPERROR`。 若要使用 `_NLSCMPERROR`，請包括 STRING.h 或 MBSTRING.h。 如果 `string1` 或 `string2` 包含定序順序之網域外部的寬字元碼，則 `_wcsncoll` 可能會失敗。 發生錯誤時，`_wcsncoll` 可能會將 `errno` 設定為 `EINVAL`。 若要檢查呼叫 `_wcsncoll` 時是否發生錯誤，請將 `errno` 設定為 0，然後在呼叫 `_wcsncoll` 之後檢查 `errno`。  
  
## <a name="remarks"></a>備註  
 所有這些函式都會根據目前使用中的字碼頁來執行 `string1` 與 `string2` 中第一個 `count` 字元的區分大小寫比較。 只有在字元集順序與字碼頁中的字典編撰字元順序不同時，以及字串比較注意這項差異時，才使用這些函式。 字元集順序是地區設定相關。 這些沒有 `_l` 後置詞之函式的版本會使用目前的地區設定，但具有 `_l` 後置詞的版本會使用傳入的地區設定。 如需詳細資訊，請參閱[地區設定](../../c-runtime-library/locale.md)。  
  
 這些函式全都會驗證它們的參數。 如果 `string1` 或 `string2` 是 Null 指標，或者 `count` 大於 `INT_MAX`，則會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果允許繼續執行，這些函式會傳回 `_NLSCMPERROR`，並將 `errno` 設為 `EINVAL`。  
  
### <a name="generic-text-routine-mappings"></a>一般文字常式對應  
  
|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsnccoll`|`_strncoll`|`_mbsncoll`|`_wcsncoll`|  
|`_tcsncoll`|`_strncoll`|[_mbsnbcoll](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)|`_wcsncoll`|  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_strncoll`, `_strncoll_l`|\<string.h>|  
|`_wcsncoll`, `_wcsncoll_l`|\<wchar.h> 或 \<string.h>|  
|`_mbsncoll`, `_mbsncoll_l`|\<mbstring.h>|  
  
 如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另請參閱  
 [地區設定](../../c-runtime-library/locale.md)   
 [字串操作](../../c-runtime-library/string-manipulation-crt.md)   
 [strcoll 函式](../../c-runtime-library/strcoll-functions.md)   
 [localeconv](../../c-runtime-library/reference/localeconv.md)   
 [_mbsnbcoll、_mbsnbcoll_l、_mbsnbicoll、_mbsnbicoll_l](../../c-runtime-library/reference/mbsnbcoll-mbsnbcoll-l-mbsnbicoll-mbsnbicoll-l.md)   
 [setlocale、_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [strcmp、wcscmp、_mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [_stricmp、_wcsicmp、_mbsicmp、_stricmp_l、_wcsicmp_l、_mbsicmp_l](../../c-runtime-library/reference/stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)   
 [strncmp、wcsncmp、_mbsncmp、_mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp、_wcsnicmp、_mbsnicmp、_strnicmp_l、_wcsnicmp_l、_mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)