---
title: "系統呼叫 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.system
dev_langs:
- C++
helpviewer_keywords:
- Windows [C++], system calls
- system calls
ms.assetid: 0255f2ec-a5a0-487e-8b09-9dad001d81ed
caps.latest.revision: 9
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
ms.translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: a802359ed0f86a7a506cf84d7a3636b57d298f84
ms.contentlocale: zh-tw
ms.lasthandoff: 03/30/2017

---
# <a name="system-calls"></a>系統呼叫
下列函式都是 Windows 作業系統呼叫。  
  
### <a name="system-call-functions"></a>系統呼叫函式  
  
|函式|用法|  
|--------------|---------|  
|[_findclose](../c-runtime-library/reference/findclose.md)|釋放先前尋找作業的資源|  
|[_findfirst、_findfirst32、_findfirst64、_findfirsti64、_findfirst32i64、_findfirst64i32、_wfindfirst、_wfindfirst32、_wfindfirst64、_wfindfirsti64、_wfindfirst32i64、_wfindfirst64i32](../c-runtime-library/reference/findfirst-functions.md)|找出具有指定屬性的檔案|  
|[_findnext、_findnext32、_findnext64、_findnexti64、_findnext32i64、_findnext64i32、_wfindnext、_wfindnext32、_wfindnexti64、_wfindnext64、_wfindnexti64](../c-runtime-library/reference/findnext-functions.md)|找出具有指定屬性的下一個檔案|  
  
## <a name="see-also"></a>另請參閱  
 [依類別區分的執行階段常式](../c-runtime-library/run-time-routines-by-category.md)   
 [檔案處理](../c-runtime-library/file-handling.md)   
 [目錄控制](../c-runtime-library/directory-control.md)   
 [低層級 I/O](../c-runtime-library/low-level-i-o.md)