---
title: "ispunct、iswpunct、_ispunct_l、_iswpunct_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "ispunct"
  - "_iswpunct_l"
  - "iswpunct"
  - "_ispunct_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "iswpunct"
  - "_istpunct"
  - "ispunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ispunct_l 函式"
  - "_istpunct 函式"
  - "_iswpunct_l 函式"
  - "ispunct 函式"
  - "ispunct_l 函式"
  - "istpunct 函式"
  - "iswpunct 函式"
  - "iswpunct_l 函式"
ms.assetid: 94403240-85c8-40a4-9c2b-e3e95c729c76
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# ispunct、iswpunct、_ispunct_l、_iswpunct_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

判斷整數是否表示標點符號字元。  
  
## 語法  
  
```  
int ispunct(  
   int c   
);  
int iswpunct(  
   wint_t c   
);  
int _ispunct_l(  
   int c,  
   _locale_t locale  
);  
int _iswpunct_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### 參數  
 `c`  
 要測試的整數。  
  
 `locale`  
 使用的地區設定。  
  
## 傳回值  
 這些常式在 `c` 是表示一個標點符號字元時回傳非零值。  `ispunct` 對所有可列印的字元，且非空白字元或字元 `isalnum` 的非零的值，傳回非零的值。  `iswpunct` 會針對不是空間寬字元和寬字元 `iswalnum` 為非零的所有可列印的寬字元的非零的值傳回非零的值。  每一個這些常式在傳入 `c` 沒有達到測試條件時回傳零。  
  
 `ispunct` 函式的測試條件結果取決於地區設定的 `LC_CTYPE` 分類設定；如需詳細資訊，請參閱 [setlocale、\_wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)。  這些函式 \(沒有 `_l` 後綴\) 的版本會使用任何地區設定相依行為的地區設定；而以 `_l` 為後綴的版本則相同，但會使用傳入的地區設定。  如需詳細資訊，請參閱[地區設定](../../c-runtime-library/locale.md)。  
  
 如果 `c` 不是 EOF 或介於 0 到 0xFF \(含\) 之間，`ispunct` 和 `_ispunct_l` 的行為是未定義。  當使用 CRT 偵錯程式庫，而 `c` 不是其中一個值時，函式會引發判斷提示。  
  
### 一般文字常式對應  
  
|TCHAR.H 常式|未定義 \_UNICODE & \_MBCS|已定義 \_MBCS|已定義 \_UNICODE|  
|----------------|----------------------------|----------------|-------------------|  
|**\_** `istpunct`|`ispunct`|[\_ismbcpunct](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswpunct`|  
  
## 需求  
  
|常式|必要的標頭|  
|--------|-----------|  
|`ispunct`|\<ctype.h\>|  
|`iswpunct`|\<ctype.h\> 或 \<wchar.h\>|  
|`_ispunct_l`|\<ctype.h\>|  
|`_iswpunct_l`|\<ctype.h\> 或 \<wchar.h\>|  
  
 如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。  
  
## 請參閱  
 [字元分類](../../c-runtime-library/character-classification.md)   
 [地區設定](../../c-runtime-library/locale.md)   
 [is、isw 常式](../../c-runtime-library/is-isw-routines.md)