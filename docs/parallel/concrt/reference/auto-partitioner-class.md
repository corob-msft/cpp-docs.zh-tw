---
title: "auto_partitioner 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
dev_langs:
- C++
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d5404f934a219649f1e8e53c1ff156a34a901f58
ms.contentlocale: zh-tw
ms.lasthandoff: 03/17/2017

---
# <a name="autopartitioner-class"></a>auto_partitioner 類別
`auto_partitioner` 類別表示 `parallel_for`、`parallel_for_each` 和 `parallel_transform` 用來分割其逐一查看之範圍的預設方法。 這種分割方法會使用範圍竊取，來進行負載平衡及逐一查看取消作業。  
  
## <a name="syntax"></a>語法  
  
```
class auto_partitioner;
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[auto_partitioner](#ctor)|建構 `auto_partitioner` 物件。|  
|[~ auto_partitioner 解構函式](#dtor)|終結 `auto_partitioner` 物件。|  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `auto_partitioner`  
  
## <a name="requirements"></a>需求  
 **標頭︰** ppl.h  
  
 **命名空間：** concurrency  
  
##  <a name="dtor"></a>~ auto_partitioner 

 終結 `auto_partitioner` 物件。  
  
```
~auto_partitioner();
```  
  
##  <a name="ctor"></a>auto_partitioner 

 建構 `auto_partitioner` 物件。  
  
```
auto_partitioner();
```  
  
## <a name="see-also"></a>另請參閱  
 [concurrency 命名空間](concurrency-namespace.md)
