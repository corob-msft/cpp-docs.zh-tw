---
title: "全域變數 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.variables"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "全域變數"
  - "全域變數, Microsoft 執行階段程式庫"
  - "變數, 全域"
ms.assetid: 01d1551c-2f0c-4f72-935c-6442caccf84f
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# 全域變數
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft C 執行階段程式庫會提供下列全域變數或巨集。  這些全域變數或巨集中，有一部分已被更安全的功能版本所取代，建議您使用這些版本而不使用全域變數。  
  
|變數|描述|  
|--------|--------|  
|[\_\_argc、\_\_argv、\_\_wargv](../c-runtime-library/argc-argv-wargv.md)|包含命令列引數。|  
|[\_daylight、\_dstbias、\_timezone 和 \_tzname](../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)|已取代。  請改用 `_get_daylight`、`_get_dstbias`、`_get_timezone` 和 `_get_tzname`。<br /><br /> 針對當地時間進行調整；用於部分日期和時間函式。|  
|[errno、\_doserrno、\_sys\_errlist 和 \_sys\_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)|已取代。  請改用 `_get_errno`、`_set_errno`、`_get_doserrno`、`_set_doserrno`、`perror` 和 `strerror`。<br /><br /> 儲存錯誤碼和相關資訊。|  
|[\_environ、\_wenviron](../c-runtime-library/environ-wenviron.md)|已取代。  請改用 `getenv_s`、`_wgetenv_s`、`_dupenv_s`、`_wdupenv_s`、`_putenv_s` 和 `_wputenv_s`。<br /><br /> 處理序環境字串指標陣列的指標；啟始時初始化。|  
|[\_fmode](../c-runtime-library/fmode.md)|已取代。  請改用 `_get_fmode` 或 `_set_fmode`。<br /><br /> 設定預設檔案轉譯模式。|  
|[\_iob](../c-runtime-library/iob.md)|主控台、檔案及裝置 I\/O 控制結構的陣列。|  
|[\_pctype、\_pwctype、\_wctype、\_mbctype、\_mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)|包含字元類別函式使用的資訊。|  
|[\_pgmptr、\_wpgmptr](../c-runtime-library/pgmptr-wpgmptr.md)|已取代。  請改用 `_get_pgmptr` 或 `_get_wpgmptr`。<br /><br /> 程式啟動時初始化為程式的完整或相對路徑、完整程式名稱或不帶副檔名的程式名稱，具體取決於如何叫用程式。|  
  
## 請參閱  
 [C 執行階段程式庫參考](../c-runtime-library/c-run-time-library-reference.md)   
 [全域常數](../c-runtime-library/global-constants.md)   
 [\_\_argc、\_\_argv、\_\_wargv](../c-runtime-library/argc-argv-wargv.md)   
 [\_get\_daylight](../c-runtime-library/reference/get-daylight.md)   
 [\_get\_dstbias](../c-runtime-library/reference/get-dstbias.md)   
 [\_get\_timezone](../c-runtime-library/reference/get-timezone.md)   
 [\_get\_tzname](../c-runtime-library/reference/get-tzname.md)   
 [perror](../c-runtime-library/reference/perror-wperror.md)   
 [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)   
 [\_get\_doserrno](../c-runtime-library/reference/get-doserrno.md)   
 [\_set\_doserrno](../c-runtime-library/reference/set-doserrno.md)   
 [\_get\_errno](../c-runtime-library/reference/get-errno.md)   
 [\_set\_errno](../c-runtime-library/reference/set-errno.md)   
 [\_dupenv\_s、\_wdupenv\_s](../c-runtime-library/reference/dupenv-s-wdupenv-s.md)   
 [getenv、\_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md)   
 [getenv\_s、\_wgetenv\_s](../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv、\_wputenv](../c-runtime-library/reference/putenv-wputenv.md)   
 [\_putenv\_s、\_wputenv\_s](../c-runtime-library/reference/putenv-s-wputenv-s.md)   
 [\_get\_fmode](../c-runtime-library/reference/get-fmode.md)   
 [\_set\_fmode](../c-runtime-library/reference/set-fmode.md)