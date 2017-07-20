---
title: _gcvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gcvt_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _gcvt_s
- gcvt_s
dev_langs:
- C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
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
ms.openlocfilehash: cc1f34eae067f0d2cc0781c9001af550b291006f
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="gcvts"></a>_gcvt_s
將浮點值轉換為字串。 這是具有 [CRT 中的安全性功能](../../c-runtime-library/security-features-in-the-crt.md)中所述之安全性增強功能的 [_gcvt](../../c-runtime-library/reference/gcvt.md) 版本。  
  
## <a name="syntax"></a>語法  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### <a name="parameters"></a>參數  
 [輸出] `buffer`  
 儲存轉換結果的緩衝區。  
  
 [in] `sizeInBytes`  
 緩衝區的大小。  
  
 [in] `value`  
 要轉換的值。  
  
 [in] `digits`  
 儲存的重要數字的數目。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則為零。 如果因為不正確的參數而發生失敗 (請參閱下表中無效的值)，會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果允許繼續執行，則會傳回錯誤碼。 錯誤碼於 Errno.h 中定義。 如需這些錯誤的清單，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
### <a name="error-conditions"></a>錯誤狀況  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|返回|`buffer` 中的值|  
|--------------|-------------------|-------------|--------------|------------|-----------------------|  
|`NULL`|任何|任何|任何|`EINVAL`|未修改。|  
|非 `NULL` (指向有效的記憶體)|零|any|任何|`EINVAL`|未修改。|  
|非 `NULL` (指向有效的記憶體)|any|任何|>= `sizeInBytes`|`EINVAL`|未修改。|  
  
 **安全性問題**  
  
 如果 `buffer` 不指向有效的記憶體，且非為 `NULL`，則 `_gcvt_s` 可能會產生存取違規。  
  
## <a name="remarks"></a>備註  
 `_gcvt_s` 函式會將浮點`value` 轉換為字元字串 (其中包括小數點和可能的正負號位元組)，並將字串儲存在 `buffer` 中。 `buffer` 應該大到足以容納轉換的值加上會自動予以附加的結束 Null 字元。 長度為 `_CVTBUFSIZE` 的緩衝區足可供任何浮點值使用。 如果使用的緩衝區大小為 `digits` + 1 ，則函式不會覆寫緩衝區結尾，因此請務必為這項作業提供足夠的緩衝區。 `_gcvt_s` 嘗試以十進位格式產生 `digits` 個數字。 如果不行，它會以指數格式產生 `digits` 個數字。 可於轉換中隱藏尾端零。  
  
 在 C++ 中，這個函式的使用已由範本多載簡化；多載可自動推斷緩衝區長度，因而不需要指定大小引數。 如需詳細資訊，請參閱[安全範本多載](../../c-runtime-library/secure-template-overloads.md)。  
  
 此函式的偵錯版本會先用 0xFD 填滿緩衝區。 若要停用此行為，請使用 [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md)。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|選擇性標頭|  
|-------------|---------------------|---------------------|  
|`_gcvt_s`|\<stdlib.h>|\<error.h>|  
  
 如需相容性的詳細資訊，請參閱＜簡介＞中的[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>範例  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 1.2  
```  
  
## <a name="see-also"></a>另請參閱  
 [資料轉換](../../c-runtime-library/data-conversion.md)   
 [浮點支援](../../c-runtime-library/floating-point-support.md)   
 [atof、_atof_l、_wtof、_wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)