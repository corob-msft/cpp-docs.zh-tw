---
title: "_ReadWriteBarrier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_ReadWriteBarrier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ReadWriteBarrier 內建"
  - "ReadWriteBarrier 內建"
ms.assetid: dd9f58b5-8bb6-494e-bb0f-9fe184f3908d
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _ReadWriteBarrier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 特定的**  
  
 限制可跨呼叫點，對記憶體存取進行重新排序的編譯器最佳化作業。  
  
> [!CAUTION]
>  `_ReadBarrier`、`_WriteBarrier` 和 `_ReadWriteBarrier` 編譯器內建物件及`MemoryBarrier` 巨集全部都已被取代，不應該再使用。  對於執行緒間通訊，請使用在 [C\+\+ Standard Library](../standard-library/cpp-standard-library-reference.md) 中定義的機制，如 [atomic\_thread\_fence](../Topic/atomic_thread_fence%20Function.md) 和 [std::atomic\<T\>](../standard-library/atomic.md)。  對於硬體存取，請使用 [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) 編譯器選項與 [volatile](../cpp/volatile-cpp.md) 關鍵字。  
  
## 語法  
  
```  
void _ReadWriteBarrier(void);  
```  
  
## 需求  
  
|內建|架構|  
|--------|--------|  
|`_ReadWriteBarrier`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **標頭檔** \<intrin.h\>  
  
## 備註  
 `_ReadWriteBarrier` 內建物件會限制可跨呼叫點，移除記憶體存取或對其進行重新排序的編譯器最佳化作業。  
  
## END Microsoft 特定的  
  
## 請參閱  
 [\_ReadBarrier](../intrinsics/readbarrier.md)   
 [\_WriteBarrier](../intrinsics/writebarrier.md)   
 [編譯器內建](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 關鍵字](../cpp/keywords-cpp.md)