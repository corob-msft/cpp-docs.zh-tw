---
title: "_ismbbkana、_ismbbkana_l | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbkana_l
- _ismbbkana
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
- _ismbbkana_l
- ismbbkana_l
- ismbbkana
- _ismbbkana
dev_langs:
- C++
helpviewer_keywords:
- _ismbbkana_l function
- _ismbbkana function
- ismbbkana function
- ismbbkana_l function
ms.assetid: 64d4eb4a-205a-40ef-be35-ff9d77fabbaf
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: ba4268b990a98059dfd5eabeef2009def809adb3
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="ismbbkana-ismbbkanal"></a>_ismbbkana、_ismbbkana_l
測試片假名符號，且為字碼頁 932 專用。  
  
## <a name="syntax"></a>語法  
  
```  
int _ismbbkana(  
   unsigned int c   
);  
int _ismbbkana_l(  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>參數  
 `c`  
 待測試整數。  
  
 `locale`  
 要使用的地區設定。  
  
## <a name="return-value"></a>傳回值  
 如果整數 `c` 是片假名符號，則 `_ismbbkana` 會傳回非零值；否則會傳回 0。 針對地區設定相關的字元資訊，`_ismbbkana` 會使用目前的地區設定。 `_ismbbkana_l` 也相同，但是它使會傳入的地區設定物件。 如需詳細資訊，請參閱[地區設定](../../c-runtime-library/locale.md)。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_ismbbkana`|\<mbctype.h>|  
|`_ismbbkana_l`|\<mbctype.h>|  
  
 如需相容性的詳細資訊，請參閱[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另請參閱  
 [位元組分類](../../c-runtime-library/byte-classification.md)   
 [_ismbb 常式](../../c-runtime-library/ismbb-routines.md)