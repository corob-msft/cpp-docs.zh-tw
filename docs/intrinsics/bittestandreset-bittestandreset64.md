---
title: "_bittestandreset _bittestandreset64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_bittestandreset64_cpp"
  - "_bittestandreset"
  - "_bittestandreset_cpp"
  - "_bittestandreset64"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "內建的 _bittestandreset"
  - "內建的 _bittestandreset64"
  - "btr 指令"
ms.assetid: 8dad63bb-a051-4cd7-a793-3357537dfeaf
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _bittestandreset _bittestandreset64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 特定的**  
  
 產生的指令會檢查位址 `a` 的位元 `b`、傳回其目前值，並將位元重設為 0。  
  
## 語法  
  
```  
unsigned char _bittestandreset(    long *a,    long b ); unsigned char _bittestandreset64(    __int64 *a,    __int64 b );  
```  
  
#### 參數  
 \[in, out\] `a`  
 要檢查的記憶體指標。  
  
 \[in\] `b`  
 要測試的位元位置。  
  
## 傳回值  
 位於指定位置的位元。  
  
## 需求  
  
|內建|架構|  
|--------|--------|  
|`_bittestandreset`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandreset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **標頭檔** \<intrin.h\>  
  
## 備註  
 此常式僅可作為內建常式使用。  
  
## 範例  
  
```  
// bittestandreset.cpp  
// processor: x86, IPF, x64  
#include <stdio.h>  
#include <limits.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandreset)  
  
// Check the sign bit and reset to 0 (taking the absolute value)  
// Returns 0 if the number is positive or zero  
// Returns 1 if the number is negative  
unsigned char absolute_value(long* p)  
{  
   const int SIGN_BIT = 31;  
   return _bittestandreset(p, SIGN_BIT);  
}  
  
int main()  
{  
    long i = -112;  
    unsigned char result;  
  
    // Check the sign bit and reset to 0 (taking the absolute value)  
  
    result = absolute_value(&i);  
    if (result == 1)  
        printf_s("The number was negative.\n");     
}  
```  
  
  **數字是負值。**   
## END Microsoft 特定的  
  
## 請參閱  
 [編譯器內建](../intrinsics/compiler-intrinsics.md)