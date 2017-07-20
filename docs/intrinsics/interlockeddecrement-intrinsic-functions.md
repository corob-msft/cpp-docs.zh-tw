---
title: "_InterlockedDecrement 內建函式 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedDecrement16_rel_cpp"
  - "_InterlockedDecrement16_acq_cpp"
  - "_InterlockedDecrement16_rel"
  - "_InterlockedDecrement64_acq"
  - "_InterlockedDecrement_nf"
  - "_InterlockedDecrement16_nf"
  - "_InterlockedDecrement64_rel_cpp"
  - "_InterlockedDecrement_rel_cpp"
  - "_InterlockedDecrement16_acq"
  - "_InterlockedDecrement64_acq_cpp"
  - "_InterlockedDecrement_rel"
  - "_InterlockedDecrement64_nf"
  - "_InterlockedDecrement16_cpp"
  - "_InterlockedDecrement64"
  - "_InterlockedDecrement_cpp"
  - "_InterlockedDecrement64_rel"
  - "_InterlockedDecrement16"
  - "_InterlockedDecrement"
  - "_InterlockedDecrement64_cpp"
  - "_InterlockedDecrement_acq"
  - "_InterlockedDecrement_acq_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedDecrement 內建函式"
  - "_InterlockedDecrement_acq 內建函式"
  - "_InterlockedDecrement_nf 內建函式"
  - "_InterlockedDecrement_rel 內建函式"
  - "_InterlockedDecrement16 內建函式"
  - "_InterlockedDecrement16_acq 內建函式"
  - "_InterlockedDecrement16_nf 內建函式"
  - "_InterlockedDecrement16_rel 內建函式"
  - "_InterlockedDecrement64 內建函式"
  - "_InterlockedDecrement64_acq 內建函式"
  - "_InterlockedDecrement64_nf 內建函式"
  - "_InterlockedDecrement64_rel 內建函式"
  - "InterlockedDecrement 內建函式"
  - "InterlockedDecrement_acq 內建函式"
  - "InterlockedDecrement_rel 內建函式"
  - "InterlockedDecrement16 內建函式"
  - "InterlockedDecrement64 內建函式"
  - "InterlockedDecrement64_acq 內建函式"
  - "InterlockedDecrement64_rel 內建函式"
ms.assetid: 5268fce3-86b5-4b2b-b96c-2e531a3fb9b5
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedDecrement 內建函式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 特定的**  
  
 提供 Win32 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] [InterlockedDecrement](http://msdn.microsoft.com/library/ms683580.aspx) 函式的編譯器內建支援。  
  
## 語法  
  
```  
long _InterlockedDecrement(  
   long * lpAddend  
);  
long _InterlockedDecrement_acq(  
   long * lpAddend  
);  
long _InterlockedDecrement_rel(  
   long * lpAddend  
);  
long _InterlockedDecrement_nf(  
   long * lpAddend  
);  
short _InterlockedDecrement16(  
   short * lpAddend  
);  
short _InterlockedDecrement16_acq(  
   short * lpAddend  
);  
short _InterlockedDecrement16_rel(  
   short * lpAddend  
);  
short _InterlockedDecrement16_nf(  
   short * lpAddend  
);  
__int64 _InterlockedDecrement64(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_acq(  
   __int64 * lpAddend  
);  
__int64 _InterlockedDecrement64_rel(  
   __int64 * lpAddend  
);   
__int64 _InterlockedDecrement64_nf(  
   __int64 * lpAddend  
);  
```  
  
#### 參數  
 \[in、out\] `lpAddend`  
 指向要遞減之變數的指標。  
  
## 傳回值  
 傳回值是所產生的遞減值。  
  
## 需求  
  
|內建|架構|  
|--------|--------|  
|`_InterlockedDecrement`, `_InterlockedDecrement16`, `_InterlockedDecrement64`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_InterlockedDecrement_acq`, `_InterlockedDecrement_rel`, `_InterlockedDecrement_nf`, `_InterlockedDecrement16_acq`, `_InterlockedDecrement16_rel`, `_InterlockedDecrement16_nf`, `_InterlockedDecrement64_acq`, `_InterlockedDecrement64_rel`, `_InterlockedDecrement64_nf`,|ARM|  
  
 **標頭檔** \<intrin.h\>  
  
## 備註  
 在 `_InterlockedDecrement` 上有數個變化，會因所涉及的資料類型，以及是否使用處理器專用的取得或釋放語意，而有所不同。  
  
 `_InterlockedDecrement` 函式在 32 位元整數值上操作，而 `_InterlockedDecrement16` 是在 16 位元整數值上操作，`_InterlockedDecrement64` 在 64 位元整數值上操作。  
  
 在 ARM 平台上，如果您需要取得並發行語意 \(例如在關鍵區段的開頭和結尾\)，請使用具有 `_acq` 和 `_rel` 後置字元的內建函式。  搭配 `_nf` \(「無範圍」\) 字尾的內建函式，不會當做記憶體屏障。  
  
 `lpAddend` 參數所指向的變數必須對齊 32 位元界限；否則，這個函式會在多處理器 x86 系統與任何非 x86 系統上失敗。  如需詳細資訊，請參閱[對齊](../cpp/align-cpp.md)。  
  
 這些常式只可做為內建函式。  
  
## 範例  
  
```  
// compiler_intrinsics_interlocked.cpp  
// compile with: /Oi  
#define _CRT_RAND_S  
  
#include <cstdlib>  
#include <cstdio>  
#include <process.h>  
#include <windows.h>  
  
// To declare an interlocked function for use as an intrinsic,  
// include intrin.h and put the function in a #pragma intrinsic   
// statement.  
#include <intrin.h>  
  
#pragma intrinsic (_InterlockedIncrement)  
  
// Data to protect with the interlocked functions.  
volatile LONG data = 1;  
  
void __cdecl SimpleThread(void* pParam);  
  
const int THREAD_COUNT = 6;  
  
int main() {  
   DWORD num;  
   HANDLE threads[THREAD_COUNT];  
   int args[THREAD_COUNT];  
   int i;  
  
   for (i = 0; i < THREAD_COUNT; i++) {  
     args[i] = i + 1;  
     threads[i] = reinterpret_cast<HANDLE>(_beginthread(SimpleThread, 0,   
                           args + i));  
      if (threads[i] == reinterpret_cast<HANDLE>(-1))  
         // error creating threads  
         break;  
   }  
  
   WaitForMultipleObjects(i, threads, true, INFINITE);  
}  
  
// Code for our simple thread  
void __cdecl SimpleThread(void* pParam) {  
   int threadNum = *((int*)pParam);  
   int counter;  
   unsigned int randomValue;  
   unsigned int time;  
   errno_t err = rand_s(&randomValue);  
  
   if (err == 0) {  
      time = (unsigned int) ((double) randomValue / (double) UINT_MAX * 500);  
      while (data < 100) {  
         if (data < 100) {  
            _InterlockedIncrement(&data);  
            printf_s("Thread %d: %d\n", threadNum, data);  
         }  
  
         Sleep(time);   // wait up to half of a second  
      }  
   }  
  
   printf_s("Thread %d complete: %d\n", threadNum, data);  
}  
```  
  
## 請參閱  
 [編譯器內建](../intrinsics/compiler-intrinsics.md)   
 [C\+\+ 關鍵字](../cpp/keywords-cpp.md)   
 [與 x86 編譯器衝突](../build/conflicts-with-the-x86-compiler.md)