---
title: "HUGE_VAL、_HUGE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 4c70ea331902ac16e99fcfa214af512f780829d8
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="hugeval-huge"></a>HUGE_VAL、_HUGE
## <a name="syntax"></a>語法  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>備註  
 `HUGE_VAL` 是最大的可表示雙精度浮點數值。 發生錯誤時，許多執行階段數學函式會傳回這個值。 針對某些函式，會傳回 -`HUGE_VAL`。 `HUGE_VAL` 定義為 `_HUGE`，但執行階段數學函式傳回 `HUGE_VAL`。 為保持一致性，您也應該在程式碼中使用 `HUGE_VAL`。  
  
## <a name="see-also"></a>另請參閱  
 [全域常數](../c-runtime-library/global-constants.md)