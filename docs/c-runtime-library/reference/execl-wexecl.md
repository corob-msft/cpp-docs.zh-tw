---
title: "_execl、_wexecl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execl
- _wexecl
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _execl
- _wexecl
- wexecl
dev_langs:
- C++
helpviewer_keywords:
- _execl function
- wexecl function
- _wexecl function
- execl function
ms.assetid: 81fefb8a-0a06-4221-b2bc-be18e38e89f4
caps.latest.revision: 23
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 670d4ddaa4209830f842c68eb84d1840e1592790
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="execl-wexecl"></a>_execl、_wexecl
載入並執行新的子處理序。  
  
> [!IMPORTANT]
>  這個 API 不能用於在 Windows 執行階段中執行的應用程式。 如需詳細資訊，請參閱 [/ZW 不支援 CRT 函式](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## <a name="syntax"></a>語法  
  
```  
intptr_t _execl(   
   const char *cmdname,  
   const char *arg0,  
   ... const char *argn,  
   NULL   
);  
intptr_t _wexecl(  
   const wchar_t *cmdname,  
   const wchar_t *arg0,  
   ... const wchar_t *argn,  
   NULL   
);  
```  
  
#### <a name="parameters"></a>參數  
 `cmdname`  
 待執行檔案的路徑。  
  
 `arg0, ... argn`  
 參數指標的清單。  
  
## <a name="return-value"></a>傳回值  
 如果成功的話，這些函式不會傳回呼叫處理序。 傳回值-1 表示錯誤，在此情況下`errno`設定全域變數。  
  
|errno 值|說明|  
|-----------------|-----------------|  
|`E2BIG`|引數和環境設定所需的空間超過 32 KB。|  
|`EACCES`|指定的檔案具有鎖定或共用違規。|  
|`EINVAL`|參數無效 (一或多個參數是 null 指標或空字串)。|  
|`EMFILE`|開啟太多檔案 (必須開啟指定的檔案，藉此判斷是否為可執行檔)。|  
|`ENOENT`|找不到該檔案或路徑。|  
|`ENOEXEC`|指定的檔案無法執行或可執行檔格式無效。|  
|`ENOMEM`|沒有足夠的記憶體可用來執行新處理序；可用的記憶體已損毀；或存在無效的區塊，表示未正確配置呼叫的處理序。|  
  
## <a name="remarks"></a>備註  
 所有這些函式都會載入和執行新的處理序，並將每個命令列引數作為個別參數傳遞。 第一個引數是命令或可執行檔名，而第二個引數應該與第一個引數相同。 它會成為所執行之處理序中的 `argv[0]`。 第三個引數是所要執行之處理序的第一個引數 `argv[1]`。  
  
 `_execl` 函式會驗證它們的參數。 如果 `cmdname` 或 `arg0` 是 null 指標或空字串，則這些函式會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。如果允許繼續執行，這些函式會將 `errno` 設定為 `EINVAL`，並傳回 -1。 沒有執行任何新處理序。  
  
## <a name="requirements"></a>需求  
  
|函式|必要的標頭|選擇性標頭|  
|--------------|---------------------|---------------------|  
|`_execl`|\<process.h>|\<errno.h>|  
|`_wexecl`|\<process.h> 或 \<wchar.h>|\<errno.h>|  
  
 如需相容性的詳細資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>範例  
 請參閱 [_exec、_wexec 函式](../../c-runtime-library/exec-wexec-functions.md)中的範例。  
  
## <a name="see-also"></a>另請參閱  
 [ 和環境控制](../../c-runtime-library/process-and-environment-control.md)   
 [_exec、_wexec 函式](../../c-runtime-library/exec-wexec-functions.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit、_Exit、_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [_onexit、_onexit_m](../../c-runtime-library/reference/onexit-onexit-m.md)   
 [_spawn、_wspawn 函式](../../c-runtime-library/spawn-wspawn-functions.md)   
 [system、_wsystem](../../c-runtime-library/reference/system-wsystem.md)