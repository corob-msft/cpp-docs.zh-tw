---
title: _heapset | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _heapset
apilocation:
- msvcr90.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr120.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _heapset
- heapset
dev_langs:
- C++
helpviewer_keywords:
- checking heap
- heapset function
- heaps, checking
- debugging [CRT], heap-related problems
- _heapset function
ms.assetid: 9667eeb0-55bc-4c19-af5f-d1fd0a142b3c
caps.latest.revision: 14
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 0bcd8094d0b07927c8f85baf81d6ae834d283d9d
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="heapset"></a>_heapset
檢查堆積是否達到基本的一致性，並將可用的項目設定為指定的值。  
  
> [!IMPORTANT]
>  此函式已被取代。 自 Visual Studio 2015 起，此函式即無法在 CRT 中使用。  
  
## <a name="syntax"></a>語法  
  
```  
int _heapset(   
   unsigned int fill   
);  
```  
  
#### <a name="parameters"></a>參數  
 `fill`  
 填滿字元。  
  
## <a name="return-value"></a>傳回值  
 `_heapset` 會傳回下列在 Malloc.h 中定義的整數資訊清單常數之一。  
  
 `_HEAPBADBEGIN`  
 找不到初始標頭資訊或其無效。  
  
 `_HEAPBADNODE`  
 堆積已損毀或找到故障的節點。  
  
 `_HEAPEMPTY`  
 堆積未初始化。  
  
 `_HEAPOK`  
 堆積看似一致。  
  
 此外若是發生錯誤， `_heapset` 會將 `errno` 設為 `ENOSYS`。  
  
## <a name="remarks"></a>備註  
 `_heapset` 函式會顯示可用的記憶體位置，或不慎被覆寫的節點。  
  
 `_heapset` 會檢查堆積是否達到基本的一致性，然後將堆積中可用項目的每個位元組設為 `fill` 值。 這項已知值會顯示堆積中的哪些記憶體位置包含可用的節點，以及所含資料中有哪些不慎被誤寫而釋放出記憶體。 若作業系統不支援 `_heapset` (例如 Windows 98)，此函數會傳回 `_HEAPOK`，並將 `errno` 設為 `ENOSYS`。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|選擇性標頭|  
|-------------|---------------------|---------------------|  
|`_heapset`|\<malloc.h>|\<errno.h>|  
  
 如需相容性的詳細資訊，請參閱＜簡介＞中的[相容性](../c-runtime-library/compatibility.md)。  
  
## <a name="example"></a>範例  
  
```  
// crt_heapset.c  
// This program checks the heap and  
// fills in free entries with the character 'Z'.  
  
#include <malloc.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int heapstatus;  
   char *buffer;  
  
   if( (buffer = malloc( 1 )) == NULL ) // Make sure heap is   
      exit( 0 );                        //    initialized       
   heapstatus = _heapset( 'Z' );        // Fill in free entries   
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf( "OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf( "OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
   free( buffer );  
}  
```  
  
```Output  
OK - heap is fine  
```  
  
## <a name="see-also"></a>另請參閱  
 [記憶體配置](../c-runtime-library/memory-allocation.md)   
 [_heapadd](../c-runtime-library/heapadd.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)