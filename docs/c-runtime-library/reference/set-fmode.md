---
title: _set_fmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_fmode
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
- _set_fmode
- set_fmode
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], default mode
- _set_fmode function
- file translation [C++], setting mode
- set_fmode function
ms.assetid: f80eb9c7-733b-4652-a9bc-6b3790a35f12
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: dae7815ba349141f746a6debc96c28829976f9d1
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="setfmode"></a>_set_fmode
設定檔案 I/O 作業的預設檔案轉譯模式。  
  
## <a name="syntax"></a>語法  
  
```  
errno_t _set_fmode(   
   int mode   
);  
```  
  
#### <a name="parameters"></a>參數  
 [in] `mode`  
 所需要的檔案轉譯模式：`_O_TEXT` 或 `_O_BINARY`。  
  
## <a name="return-value"></a>傳回值  
 如果成功，會傳回零；如果失敗，則傳回錯誤碼。 如果 `mode` 不是 `_O_TEXT`、`_O_BINARY` 或 `_O_WTEXT`，則會叫用無效的參數處理常式，如[參數驗證](../../c-runtime-library/parameter-validation.md)中所述。 若允許繼續執行，此函式會將 `errno` 設為 `EINVAL`，並傳回 `EINVAL`。  
  
## <a name="remarks"></a>備註  
 此函式會設定 [_fmode](../../c-runtime-library/fmode.md) 全域變數。 此變數為檔案 I/O 作業 `_open` 和 `_pipe` 指定預設檔案轉譯模式。  
  
 `_O_TEXT` 和 `_O_BINARY` 定義於 Fcntl.h。 `EINVAL` 定義於 Errno.h。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|選擇性標頭|  
|-------------|---------------------|---------------------|  
|`_set_fmode`|\<stdlib.h>|\<fcntl.h>、\<errno.h>|  
  
 如需相容性詳細資訊，請參閱＜簡介＞中的[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>範例  
  
```  
// crt_set_fmode.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <fcntl.h>     /* for _O_TEXT and _O_BINARY */  
#include <errno.h>     /* for EINVAL */  
#include <sys\stat.h>  /* for _S_IWRITE */  
#include <share.h>     /* for _SH_DENYNO */  
  
int main()  
{  
   int mode, fd, ret;  
   errno_t err;  
   int buf[12] = { 65, 66, 67, 68, 69, 70, 71, 72, 73, 74,  
                   75, 76 };  
   char * filename = "fmode.out";  
  
   err = _get_fmode(&mode);  
   if (err == EINVAL)  
   {  
      printf( "Invalid parameter: mode\n");  
      return 1;  
   }  
   else  
      printf( "Default Mode is %s\n", mode == _O_TEXT ? "text" :  
              "binary");  
  
   err = _set_fmode(_O_BINARY);  
   if (err == EINVAL)  
   {  
      printf( "Invalid mode.\n");  
      return 1;  
   }  
  
   if ( _sopen_s(&fd, filename, _O_RDWR | _O_CREAT, _SH_DENYNO, _S_IWRITE | _S_IREAD) != 0 )  
   {  
      printf( "Error opening the file %s\n", filename);  
      return 1;  
   }  
  
   if (ret = _write(fd, buf, 12*sizeof(int)) < 12*sizeof(int))  
   {  
      printf( "Problem writing to the file %s.\n", filename);  
      printf( "Number of bytes written: %d\n", ret);  
   }  
  
   if (_close(fd) != 0)  
   {  
      printf("Error closing the file %s. Error code %d.\n",  
             filename, errno);  
   }  
  
   system("type fmode.out");  
}  
```  
  
```Output  
Default Mode is binary  
A   B   C   D   E   F   G   H   I   J   K   L     
```  
  
## <a name="see-also"></a>另請參閱  
 [_fmode](../../c-runtime-library/fmode.md)   
 [_get_fmode](../../c-runtime-library/reference/get-fmode.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [文字和二進位模式檔案 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)