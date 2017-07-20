---
title: "_execvpe、_wexecvpe | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _execvpe
- _wexecvpe
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
- wexecvpe
- execvpe
- _wexecvpe
- _execvpe
dev_langs:
- C++
helpviewer_keywords:
- wexecvpe function
- execvpe function
- _wexecvpe function
- _execvpe function
ms.assetid: c0c3c986-d9c0-4814-a96c-10f0b3092766
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
ms.openlocfilehash: fc5a0df49b31f77874e6a75ff39ed9650386c58f
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="execvpe-wexecvpe"></a>_execvpe、_wexecvpe
載入並執行新的子處理序。  
  
> [!IMPORTANT]
>  這個應用程式開發介面不能用於 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)] 中執行的應用程式。 如需詳細資訊，請參閱 [/ZW 不支援 CRT 函式](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx)。  
  
## <a name="syntax"></a>語法  
  
```  
intptr_t _execvpe(   
   const char *cmdname,  
   const char *const *argv,  
   const char *const *envp   
);  
intptr_t _wexecvpe(   
   const wchar_t *cmdname,  
   const wchar_t *const *argv,  
   const wchar_t *const *envp   
);  
```  
  
#### <a name="parameters"></a>參數  
 `cmdname`  
 待執行檔案的路徑。  
  
 `argv`  
 參數指標的陣列。  
  
 `envp`  
 環境設定的指標陣列。  
  
## <a name="return-value"></a>傳回值  
 如果成功的話，這些函式不會傳回呼叫處理序。 傳回值-1 表示錯誤，在此情況下`errno`設定全域變數。  
  
|`errno` 值|說明|  
|-------------------|-----------------|  
|`E2BIG`|引數和環境設定所需的空間超過 32 KB。|  
|`EACCES`|指定的檔案具有鎖定或共用違規。|  
|`EMFILE`|已開啟太多檔案。 (必須開啟指定的檔案，藉此判斷是否為可執行檔。)|  
|`ENOENT`|找不到該檔案或路徑。|  
|`ENOEXEC`|指定的檔案無法執行或可執行檔格式無效。|  
|`ENOMEM`|沒有足夠的記憶體可用來執行新處理序；可用的記憶體已損毀；或存在無效的區塊，表示未正確配置呼叫的處理序。|  
  
 如需這些傳回碼和其他傳回碼的詳細資訊，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>備註  
 這些函式中的每一個都會載入和執行新處理序，並傳遞命令列引數的指標陣列和環境設定的指標陣列。 這些函式使用 `PATH` 環境變數來尋找要執行的檔案。  
  
 `_execvpe` 函式會驗證它們的參數。 如果 `cmdname` 為 Null 指標，或如果 `argv` 為 Null 指標 (空陣列的指標)，或陣列指標包含作為第一個引數的空字串，則這些函式會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果允許繼續執行，這些函式會將 `errno` 設定為 `EINVAL` ，並傳回 -1。 未啟動任何處理序。  
  
## <a name="requirements"></a>需求  
  
|函式|必要的標頭|選擇性標頭|  
|--------------|---------------------|---------------------|  
|`_execvpe`|\<process.h>|\<errno.h>|  
|`_wexecvpe`|\<process.h> 或 \<wchar.h>|\<errno.h>|  
  
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