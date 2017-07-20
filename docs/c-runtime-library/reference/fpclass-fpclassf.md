---
title: "_fpclass、_fpclassf | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fpclass
- _fpclassf
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs:
- C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9f061841ea6f4050945caeb2cacb9acfdce77c44
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="fpclass-fpclassf"></a>_fpclass、_fpclassf
傳回一個值，指出引數的浮點分類。  
  
## <a name="syntax"></a>語法  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>參數  
 `x`  
 要測試的浮點值。  
  
## <a name="return-value"></a>傳回值  
 `_fpclass` 和 `_fpclassf` 函式會傳回整數值，指出 `x` 引數的浮點分類。 分類可能會有 \<float.h> 中所定義的下列其中一個值。  
  
|值|描述|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|訊號 NaN|  
|`_FPCLASS_QNAN`|無訊息 NaN|  
|`_FPCLASS_NINF`|無限大的負數 (-INF)|  
|`_FPCLASS_NN`|負標準化非零|  
|`_FPCLASS_ND`|負異常化|  
|`_FPCLASS_NZ`|負零 （-0）|  
|`_FPCLASS_PZ`|正 0 (+0)|  
|`_FPCLASS_PD`|正異常化|  
|`_FPCLASS_PN`|正標準化非零|  
|`_FPCLASS_PINF`|正無限大 (+INF)|  
  
## <a name="remarks"></a>備註  
 `_fpclass` 和 `_fpclassf` 函式為 Microsoft 特有。 它們與 [fpclassify](../../c-runtime-library/reference/fpclassify.md) 類似，但傳回引數的更多詳細資訊。 只有在針對 x64 平台進行編譯時，才能使用 `_fpclassf` 函式。  
  
## <a name="requirements"></a>需求  
  
|函式|必要的標頭|  
|--------------|---------------------|  
|`_fpclass`|\<float.h>|  
  
 如需相容性和一致性的詳細資訊，請參閱[相容性](../../c-runtime-library/compatibility.md)。  
  
## <a name="see-also"></a>另請參閱  
 [浮點支援](../../c-runtime-library/floating-point-support.md)   
 [isnan、_isnan、_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)