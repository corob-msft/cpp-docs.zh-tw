---
title: _CrtGetDumpClient | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtGetDumpClient
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
- CrtGetDumpClient
- _CrtGetDumpClient
dev_langs:
- C++
helpviewer_keywords:
- _CrtGetDumpClient function
- CrtGetDumpClient function
ms.assetid: 9051867f-341b-493b-b53d-45d2b454a3ad
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 941fc0ffdeb691b599ceb8c79d4439da4d36dd7f
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="crtgetdumpclient"></a>_CrtGetDumpClient
擷取目前的應用程式定義函式，以傾印 `_CLIENT_BLOCK` 類型記憶體區塊 (僅限偵錯版本)。  
  
## <a name="syntax"></a>語法  
  
```  
_CRT_DUMP_CLIENT _CrtGetDumpClient( void );  
```  
  
## <a name="return-value"></a>傳回值  
 傳回目前的傾印常式。  
  
## <a name="remarks"></a>備註  
 `_CrtGetDumpClient` 函式會針對 C 執行階段偵錯記憶體傾印處理序，擷取儲存在 `_CLIENT_BLOCK` 記憶體區塊中之傾印物件的目前攔截函式。  
  
 如需使用支援攔截程序之其他執行階段函式，以及撰寫您自己的用戶端定義攔截函式的詳細資訊，請參閱[撰寫偵錯攔截函式](/visualstudio/debugger/debug-hook-function-writing)。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_CrtGetDumpClient`|\<crtdbg.h>|  
  
 如需相容性的詳細資訊，請參閱＜簡介＞中的[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>程式庫  
 僅限偵錯版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯常式](../../c-runtime-library/debug-routines.md)   
 [_CrtReportBlockType](../../c-runtime-library/reference/crtreportblocktype.md)   
 [_CrtSetDumpClient](../../c-runtime-library/reference/crtsetdumpclient.md)