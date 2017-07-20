---
title: "_access、_waccess | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _access
- _waccess
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _waccess
- _access
- taccess
- waccess
- _taccess
dev_langs:
- C++
helpviewer_keywords:
- access function
- _taccess function
- waccess function
- _access function
- _waccess function
- taccess function
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
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
ms.openlocfilehash: d0968ec14a43cfbbf1169f34ac929435787bc349
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="access-waccess"></a>_access、_waccess
判斷檔案是否為唯讀。 這些函式有更安全的版本可用，請參閱 [_access_s、_waccess_s](../../c-runtime-library/reference/access-s-waccess-s.md)。  
  
## <a name="syntax"></a>語法  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### <a name="parameters"></a>參數  
 `path`  
 檔案或目錄路徑。  
  
 `mode`  
 讀取/寫入屬性。  
  
## <a name="return-value"></a>傳回值  
 如果檔案有指定模式，每個函式都會傳回 0。 如果具名的檔案不存在或沒有指定的模式;，函數會傳回-1在此情況下，`errno`會設定為下表所示。  
  
 `EACCES`  
 拒絕存取：檔案的權限設定不允許指定的存取。  
  
 `ENOENT`  
 找不到檔案名稱或路徑。  
  
 `EINVAL`  
 無效的參數。  
  
 如需這些傳回碼和其他傳回碼的詳細資訊，請參閱 [_doserrno、errno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。  
  
## <a name="remarks"></a>備註  
 搭配檔案使用時，`_access` 函式會判斷指定的檔案或目錄是否存在，以及是否有 `mode` 值指定的屬性。 搭配目錄使用時，`_access` 只判斷指定的目錄是否存在；在 [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] 及更新的作業系統中，所有目錄都有讀取和寫入存取權。  
  
|`mode` 值|檢查檔案|  
|------------------|---------------------|  
|00|只存在|  
|02|唯寫|  
|04|唯讀|  
|06|讀取和寫入|  
  
 此函式只檢查檔案和目錄是否為唯讀，不檢查檔案系統安全性設定。 該項作業需要存取權杖。 如需檔案系統安全性的詳細資訊，請參閱 [Access Tokens](http://msdn.microsoft.com/library/windows/desktop/aa374909) (存取權杖)。 ATL 類別的存在就是提供這項功能，請參閱 [CAccessToken 類別](../../atl/reference/caccesstoken-class.md)。  
  
 `_waccess` 是寬字元版本的 `_access`；`path` 的 `_waccess` 引數是寬字元字串。 否則，`_waccess` 和 `_access` 的行為即會相同。  
  
 這個函式會驗證它的參數。 如果 `path` 是 `NULL`，或 `mode` 不指定有效的模式，則會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 如果允許繼續執行，則函式會將 `errno` 設定為 `EINVAL` 並傳回 -1。  
  
### <a name="generic-text-routine-mappings"></a>一般文字常式對應  
  
|Tchar.h 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|選擇性標頭|  
|-------------|---------------------|----------------------|  
|`_access`|\<io.h>|\<errno.h>|  
|`_waccess`|\<wchar.h> 或 \<io.h>|\<errno.h>|  
  
## <a name="example"></a>範例  
 下例會使用 `_access` 檢查名為 crt_ACCESS.C 的檔案，以查看它是否存在以及是否允許寫入。  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
```Output  
File crt_ACCESS.C exists.  
File crt_ACCESS.C does not have write permission.  
```  
  
## <a name="see-also"></a>另請參閱  
 [檔案處理](../../c-runtime-library/file-handling.md)   
 [_chmod、_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat、_wstat 函式](../../c-runtime-library/reference/stat-functions.md)