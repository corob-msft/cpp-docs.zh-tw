---
title: _RTC_SetErrorFuncW | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _RTC_SetErrorFuncW
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
- _RTC_SetErrorFuncW
- RTC_SetErrorFuncW
dev_langs:
- C++
helpviewer_keywords:
- run-time errors
- RTC_SetErrorFuncW function
- _RTC_error_fnW typedef
- _RTC_SetErrorFuncW function
- RTC_error_fnW typedef
ms.assetid: b3e0d71f-1bd3-4c37-9ede-2f638eb3c81a
caps.latest.revision: 15
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9c340310feb94ac181049c01d3ab1efaee2002c3
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="rtcseterrorfuncw"></a>_RTC_SetErrorFuncW
指定函式做為報告執行階段錯誤檢查 (RTC) 的處理常式。  
  
## <a name="syntax"></a>語法  
  
```  
  
      _RTC_error_fnW _RTC_SetErrorFuncW(  
   _RTC_error_fnW function   
);  
```  
  
#### <a name="parameters"></a>參數  
 `function`  
 函式的位址，會處理執行階段錯誤檢查。  
  
## <a name="return-value"></a>傳回值  
 先前定義的錯誤函式。若先前未曾定義函式，即為 `NULL`。  
  
## <a name="remarks"></a>備註  
 在新程式碼中，請一律使用 `_RTC_SetErrorFuncW`。 程式庫中只包含`_RTC_SetErrorFunc` 供回溯相容性之用。  
  
 `_RTC_SetErrorFuncW` 回呼僅適用其所連結的元件，而非適用於全域。  
  
 請確定您將傳遞給 `_RTC_SetErrorFuncW` 的位址是有效錯誤處理函式的位址。  
  
 如果錯誤已被指派為-1 的類型使用[_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md)，則不會呼叫錯誤處理函式。  
  
 您必須先呼叫任一個執行階段錯誤檢查初始化函式，才能呼叫此函式。 如需詳細資訊，請參閱 [Using Run-Time Checks Without the C Run-Time Library](/visualstudio/debugger/using-run-time-checks-without-the-c-run-time-library)。  
  
 **_RTC_error_fnW** 的定義如下：  
  
 **typedef int (__cdecl \*_RTC_error_fnW)(int**  `errorType` **, const wchar_t \*** *filename* **, int**  <行號> **, const wchar_t \*** `moduleName` **, const wchar_t \*** <格式> **, ...);**  
  
 其中：  
  
 `errorType`  
 [_RTC_SetErrorType](../../c-runtime-library/reference/rtc-seterrortype.md)所指定之錯誤的類型。  
  
 *filename*  
 發生失敗的來源檔案；若無偵錯資訊，即為 null。  
  
 *linenumber*  
 發生錯誤之 *檔案名稱* 中的行；若無偵錯資訊，即為 0。  
  
 `moduleName`  
 發生失敗之 DLL 或可執行檔的名稱。  
  
 *格式*  
 printf 樣式字串，可使用剩餘的參數顯示錯誤訊息。 VA_ARGLIST 的第一個引數是所發生的 RTC 錯誤號碼。  
  
 如需示範如何使用 **_RTC_error_fnW** 的範例，請參閱[自訂原生執行階段檢查](/visualstudio/debugger/native-run-time-checks-customization)。  
  
## <a name="requirements"></a>需求  
  
|常式|必要的標頭|  
|-------------|---------------------|  
|`_RTC_SetErrorFuncW`|\<rtcapi.h>|  
  
 如需詳細資訊，請參閱[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="libraries"></a>程式庫  
 所有版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。  
  
## <a name="see-also"></a>另請參閱  
 [_CrtDbgReport、_CrtDbgReportW](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md)   
 [執行階段錯誤檢查](../../c-runtime-library/run-time-error-checking.md)