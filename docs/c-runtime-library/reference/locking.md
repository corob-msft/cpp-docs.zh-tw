---
title: _locking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _locking
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
- _locking
dev_langs:
- C++
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
caps.latest.revision: 19
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
ms.openlocfilehash: 7789a1634f5ee87d54d6b9f2aadbc720819f31ef
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="locking"></a>_locking
鎖定或解除鎖定檔案的位元組。  
  
## <a name="syntax"></a>語法  
  
```  
  
      int _locking(  
   int fd,  
   int mode,  
   long nbytes   
);  
```  
  
#### <a name="parameters"></a>參數  
 `fd`  
 檔案描述項。  
  
 *mode*  
 要執行的鎖定動作。  
  
 *nbytes*  
 要鎖定的位元組數目。  
  
## <a name="return-value"></a>傳回值  
 如果成功，`_locking` 會傳回 0。 傳回值-1 表示失敗，在此情況下[errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)設為下列值之一。  
  
 `EACCES`  
 鎖定違規 (檔案已鎖定或解除鎖定)。  
  
 `EBADF`  
 檔案描述項無效。  
  
 `EDEADLOCK`  
 鎖定違規。 指定 `_LK_LOCK` 或 `_LK_RLCK` 旗標，而且檔案在嘗試 10 次後無法鎖定時傳回。  
  
 `EINVAL`  
 指定給 `_locking` 的引數無效。  
  
 如果由於參數不正確而失敗 (例如檔案描述項無效)，則會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。  
  
## <a name="remarks"></a>備註  
 `_locking` 函式會鎖定或解除鎖定 `fd` 所指定之檔案的 *nbytes* 個位元組。 鎖定檔案中的位元組可防止其他處理序存取這些位元組。 所有鎖定或解除鎖定都會從檔案指標的目前位置開始，並接著繼續進行 *nbytes* 個位元組。 您可以鎖定超過檔案結尾的位元組。  
  
 *mode* 必須是定義於 Locking.h 中的下列其中一個資訊清單常數。  
  
 `_LK_LOCK`  
 鎖定指定的位元組。 如果無法鎖定位元組，程式會在 1 秒後立即重試。 如果嘗試 10 次之後還是無法鎖定位元組，常數會傳回錯誤。  
  
 `_LK_NBLCK`  
 鎖定指定的位元組。 如果無法鎖定位元組，常數會傳回錯誤。  
  
 `_LK_NBRLCK`  
 與 `_LK_NBLCK` 相同。  
  
 `_LK_RLCK`  
 與 `_LK_LOCK` 相同。  
  
 `_LK_UNLCK`  
 解除鎖定指定的位元組，這些位元組之前必須已鎖定。  
  
 可鎖定檔案中多個不重疊的區域。 要解除鎖定的區域之前必須已鎖定。 `_locking` 不會合併相鄰區域；如果兩個鎖定的區域相鄰，則必須個別解除鎖定每個區域。 區域只能短暫鎖定，而且必須在關閉檔案或結束程式之前解除鎖定。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|選擇性標頭|  
|-------------|---------------------|---------------------|  
|`_locking`|\<io.h> 和 \<sys/locking.h>|\<errno.h>|  
  
 如需相容性的詳細資訊，請參閱＜簡介＞中的[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>程式庫  
 所有版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。  
  
## <a name="example"></a>範例  
  
```  
// crt_locking.c  
/* This program opens a file with sharing. It locks  
 * some bytes before reading them, then unlocks them. Note that the  
 * program works correctly only if the file exists.  
 */  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/locking.h>  
#include <share.h>  
#include <fcntl.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <io.h>  
  
int main( void )  
{  
   int  fh, numread;  
   char buffer[40];  
  
   /* Quit if can't open file or system doesn't   
    * support sharing.   
    */  
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,   
                          _S_IREAD | _S_IWRITE );  
   printf( "%d %d\n", err, fh );  
   if( err != 0 )  
      exit( 1 );  
  
   /* Lock some bytes and read them. Then unlock. */  
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )  
   {  
      long lseek_ret;  
      printf( "No one can change these bytes while I'm reading them\n" );  
      numread = _read( fh, buffer, 30 );  
      buffer[30] = '\0';  
      printf( "%d bytes read: %.30s\n", numread, buffer );  
      lseek_ret = _lseek( fh, 0L, SEEK_SET );  
      _locking( fh, LK_UNLCK, 30L );  
      printf( "Now I'm done. Do what you will with them\n" );  
   }  
   else  
      perror( "Locking failed\n" );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtlockingtxt"></a>輸入︰crt_locking.txt  
  
```  
The first thirty bytes of this file will be locked.  
```  
  
## <a name="sample-output"></a>範例輸出  
  
```  
No one can change these bytes while I'm reading them  
30 bytes read: The first thirty bytes of this  
Now I'm done. Do what you will with them  
```  
  
## <a name="see-also"></a>另請參閱  
 [檔案處理](../../c-runtime-library/file-handling.md)   
 [_creat、_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open、_wopen](../../c-runtime-library/reference/open-wopen.md)