---
title: "lock::release | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "lock.release"
  - "msclr::lock::release"
  - "lock::release"
  - "msclr.lock.release"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::release"
ms.assetid: b73d48fc-cf98-4b78-b39d-813d4a12fa84
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# lock::release
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

釋放鎖定。  
  
## 語法  
  
```  
void release();  
```  
  
## 備註  
 如果鎖定不保留， `release` 不會有任何作用。  
  
 您不需要明確地呼叫這個函式;當 `lock` 物件超出範圍時，其解構函式呼叫 `release`。  
  
## 範例  
 這個範例使用類別的單一執行個體跨多個執行緒的。類別會使用自己的鎖定確保對其內部資料的存取權為每個執行緒是一致的。主應用程式執行緒使用類別的同一個執行個體上具有鎖定定期檢查任何背景工作執行緒是否仍存在，而且會結束，直到所有背景工作執行緒完成其工作。  
  
```  
// msl_lock_release.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
  **在執行緒 3，計數器 \= 0**  
**在執行緒 3，計數器 \= 10**  
**在執行緒 5，計數器 \= 0**  
**在執行緒 5，計數器 \= 10**  
**在執行緒 7，計數器 \= 0**  
**在執行緒 7，計數器 \= 10**  
**在執行緒 4，計數器 \= 0**  
**在執行緒 4，計數器 \= 10**  
**在執行緒 6，計數器 \= 0**  
**在執行緒 6，計數器 \= 10**  
**任何執行緒完成。**   
## 需求  
 **標頭檔** \<msclr \\ lock.h\>  
  
 **命名空間** msclr  
  
## 請參閱  
 [lock 成員](../dotnet/lock-members.md)   
 [lock::~lock](../dotnet/lock-tilde-lock.md)