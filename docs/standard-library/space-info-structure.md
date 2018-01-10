---
title: "space_info 結構 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::tr2::sys::space_info
dev_langs: C++
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b59a50a4040756ffb32cda12c6abb08ba0cfbe1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2017
---
# <a name="spaceinfo-structure"></a>space_info 結構
保留磁碟區的相關資訊。  
  
## <a name="syntax"></a>語法  
  
```  
struct space_info   {
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
    };  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-data-members"></a>公用資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|`unsigned long long available`|表示可用來代表磁碟區資料的位元組數目。|  
|`unsigned long long capacity`|表示磁碟區可以表示的總位元組數目。|  
|`unsigned long long free`|表示不用來代表磁碟區資料的位元組數目。|  
  
## <a name="requirements"></a>需求  
 **標頭：** \<filesystem >  
  
 **命名空間：**std::experimental::filesystem  
  
## <a name="see-also"></a>另請參閱  
 [標頭檔參考](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)   
 [空間](http://msdn.microsoft.com/en-us/7fce0b0e-523b-4598-b218-47245d0204ca)   
 [檔案系統巡覽 (C++)](../standard-library/file-system-navigation.md)
