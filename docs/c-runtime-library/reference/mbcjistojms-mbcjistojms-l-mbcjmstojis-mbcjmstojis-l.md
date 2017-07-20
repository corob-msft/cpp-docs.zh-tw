---
title: "_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
apitype: DLLExport
f1_keywords:
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
dev_langs:
- C++
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
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
ms.openlocfilehash: 514e00148ec34a14a7b229d5b7e226d8be66636d
ms.contentlocale: zh-tw
ms.lasthandoff: 04/04/2017

---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l
在日本業界標準 (JIS) 和日本 Microsoft (JMS) 字元之間進行轉換。  
  
> [!IMPORTANT]
>  這個 API 不能用於在 Windows 執行階段中執行的應用程式。 如需詳細資訊，請參閱 [/ZW 不支援 CRT 函式](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## <a name="syntax"></a>語法  
  
```  
unsigned int _mbcjistojms(  
   unsigned int c   
);  
unsigned int _mbcjistojms_l(  
   unsigned int c,  
   _locale_t locale  
);  
unsigned int _mbcjmstojis(  
   unsigned int c   
);  
unsigned int _mbcjmstojis_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>參數  
 `c`  
 要轉換的字元。  
  
 `local`  
 要使用的地區設定。  
  
## <a name="return-value"></a>傳回值  
 在日本地區設定，這些函式會傳回已轉換的字元；如果無法轉換，則傳回 0。 在非日文地區設定，這些函式會傳回傳入的字元。  
  
## <a name="remarks"></a>備註  
 `_mbcjistojms` 函式會將日本業界標準 (JIS) 字元轉換成 Microsoft 漢字 (Shift JIS) 字元。 只有前置和後隨位元組 0x21-0x7E 範圍中，將轉換的字元。 如果前導位元組或後隨位元組超出此範圍，`errno` 會設定為 `EILSEQ`。 如需此錯誤碼和其他錯誤碼的詳細資訊，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
 `_mbcjmstojis`函式會將 Shift JIS 字元轉換為 JIS 字元。 只有前導位元組處於範圍 0x81-0x9F 或 0xE0-0xFC 且為在範圍內 0x40-0x7E 或 0x80-0xFC 的後隨位元組，將轉換的字元。 請注意，該範圍內的某些字碼指標未指派一個字元，因此無法進行轉換。  
  
 值 `c` 應該是 16 位元值，其較高的 8 位元代表要轉換之字元的前導位元組，而其較低的 8 位元代表後隨位元組。  
  
 輸出值會受到地區設定的 `LC_CTYPE` 分類設定影響；如需詳細資訊，請參閱 [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)。 這些沒有 `_l` 後置字元的函式版本，會針對此與地區設定相關的行為使用目前的地區設定；具有 `_l` 後置字元的版本也一樣，只不過它們會改用傳遞的地區設定參數。 如需詳細資訊，請參閱 [Locale](../../c-runtime-library/locale.md)。  
  
 在舊版中，`_mbcjistojms`和`_mbcjmstojis`所呼叫`jistojms`和`jmstojis`分別。 `_mbcjistojms``_mbcjistojms_l`，`_mbcjmstojis`和`_mbcjmstojis_l`應該改用。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_mbcjistojms`|\<mbstring.h>|  
|`_mbcjistojms_l`|\<mbstring.h>|  
|`_mbcjmstojis`|\<mbstring.h>|  
|`_mbcjmstojis_l`|\<mbstring.h>|  
  
 如需相容性的詳細資訊，請參閱[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另請參閱  
 [資料轉換](../../c-runtime-library/data-conversion.md)   
 [_ismbb 常式](../../c-runtime-library/ismbb-routines.md)