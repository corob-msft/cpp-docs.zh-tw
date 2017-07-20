---
title: _free_dbg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
caps.latest.revision: 16
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
ms.openlocfilehash: da04eb912452b14250704bb2aba2af35fd30d409
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="freedbg"></a>_free_dbg
釋放堆積中的記憶體區塊 (僅限偵錯版本)。  
  
## <a name="syntax"></a>語法  
  
```  
void _free_dbg(   
   void *userData,  
   int blockType   
);  
```  
  
#### <a name="parameters"></a>參數  
 `userData`  
 要釋放之已配置記憶體區塊的指標。  
  
 `blockType`  
 要釋放之已配置記憶體區塊的類型：`_CLIENT_BLOCK`、`_NORMAL_BLOCK` 或 `_IGNORE_BLOCK`。  
  
## <a name="remarks"></a>備註  
 `_free_dbg` 函式是偵錯版本的 [free](../../c-runtime-library/reference/free.md) 函式。 未定義 [_DEBUG](../../c-runtime-library/debug.md) 時，每個 `_free_dbg` 呼叫都會降至 `free` 呼叫。 `free` 和 `_free_dbg` 都會釋放基底堆積中的記憶體區塊，但 `_free_dbg` 容納兩個偵錯功能：將釋放的區塊保留在堆積的已連結清單中以模擬低記憶體狀況的能力，以及釋放特定配置類型的區塊類型參數。  
  
 `_free_dbg` 會先對所有指定檔案和區塊位置執行有效性檢查，再執行釋放作業。 應用程式不需要提供此資訊。 釋放記憶體區塊時，偵錯堆積管理員會自動檢查使用者部分每一端的緩衝區完整性，並在發生覆寫時發出錯誤報表。 如果設定 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md) 旗標的 `_CRTDBG_DELAY_FREE_MEM_DF` 位元欄位，會以值 0xDD 填入釋放的區塊，並獲指派 `_FREE_BLOCK` 區塊類型，而且會保留在堆積的已連結記憶體區塊清單中。  
  
 若釋放記憶體發生錯誤，會使用來自作業系統且具有失敗性質的資訊設定 `errno`。 如需詳細資訊，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
 如需在偵錯版本的基底堆積中如何配置、初始化及管理記憶體區塊的資訊，請參閱 [CRT 偵錯堆積詳細資料](/visualstudio/debugger/crt-debug-heap-details)。 如需配置區塊類型以及如何使用它們的資訊，請參閱[偵錯堆積上的區塊類型](/visualstudio/debugger/crt-debug-heap-details)。 如需在應用程式的偵錯組建中呼叫標準堆積函式以及其偵錯版本之間的差異的資訊，請參閱[堆積配置函式的偵錯版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_free_dbg`|\<crtdbg.h>|  
  
 如需相容性的詳細資訊，請參閱＜簡介＞中的[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>範例  
 如需如何使用 `_free_dbg` 的範例，請參閱 [crt_dbg2](http://msdn.microsoft.com/en-us/21e1346a-6a17-4f57-b275-c76813089167)。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯常式](../../c-runtime-library/debug-routines.md)   
 [_malloc_dbg](../../c-runtime-library/reference/malloc-dbg.md)