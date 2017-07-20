---
title: "sampler 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
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
ms.openlocfilehash: f81208e40cb2a211b714af1efe801e81cd567374
ms.contentlocale: zh-tw
ms.lasthandoff: 03/17/2017

---
# <a name="sampler-class"></a>sampler 類別
取樣器類別會彙總使用的紋理取樣的取樣組態資訊。  
  
## <a name="syntax"></a>語法  
  
```  
class sampler;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[取樣器建構函式](#ctor)|多載。 建構的取樣器執行個體。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[get_address_mode](#get_address_mode)|傳回`address_mode`取樣器物件與關聯。|  
|[get_border_color](#get_border_color)|傳回具有相關聯的取樣器物件的框線色彩。|  
|[get_filter_mode](#get_filter_mode)|傳回`filter_mode`取樣器物件與關聯。|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|說明|  
|----------|-----------------|  
|[operator=](#operator_eq)|多載。 指派運算子。|  
  
### <a name="public-data-members"></a>公用資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|[address_mode](#address_mode)|取得的地址模式`sampler`物件。|  
|[border_color](#border_color)|取得框線的色彩`sampler`物件。|  
|[filter_mode](#filter_mode)|取得篩選條件模式`sampler`物件。|  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `sampler`  
  
## <a name="requirements"></a>需求  
 **標頭︰** amp_graphics.h  
  
 **命名空間︰** concurrency:: graphics  
  
##  <a name="ctor"></a>取樣器 

 建構的執行個體[sampler 類別](sampler-class.md)。  
  
```  
sampler() restrict(cpu);

 *// [1] default constructor  
 
sampler(// [2] constructor  
    filter_mode _Filter_mode) restrict(cpu);

 
sampler(// [3] constructor  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [4] constructor  
    filter_mode _Filter_mode,  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [5] copy constructor  
    const sampler& _Other) restrict(amp,
    cpu);

 
sampler(// [6] move constructor  
    sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>參數  
 `_Filter_mode`  
 要用於取樣的篩選模式。  
  
 `_Address_mode`  
 用於取樣中之所有維度的定址模式。  
  
 `_Border_color`  
 如果位址模式是 address_border 使用之框線色彩。 預設值是 `float_4(0.0f, 0.0f, 0.0f, 0.0f)`。  
  
 `_Other`  
 [5] 複製建構函式  
 `sampler`要複製到新物件`sampler`執行個體。  
  
 [6] 移動建構函式  
 `sampler`移動到新物件`sampler`執行個體。  
  
##  <a name="address_mode"></a>address_mode 

 取得的地址模式`sampler`物件。  
  
```  
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;  
```  
  
##  <a name="border_color"></a>border_color 

 取得框線的色彩`sampler`物件。  
  
```  
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;  
```  
  
##  <a name="filter_mode"></a>filter_mode 

 取得篩選條件模式`sampler`物件。  
  
```  
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;  
```  
  
##  <a name="get_address_mode"></a>get_address_mode 

 傳回這個設定的篩選條件模式`sampler`。  
  
```  
Concurrency::graphics::address_mode get_address_mode() const __GPU;  
```  
  
### <a name="return-value"></a>傳回值  
 已設定之取樣器位址模式。  
  
##  <a name="get_border_color"></a>get_border_color 

 傳回設定的框線色彩`sampler`。  
  
```  
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>傳回值  
 Float_4 包含框線色彩。  
  
##  <a name="get_filter_mode"></a>get_filter_mode 

 傳回這個設定的篩選條件模式`sampler`。  
  
```  
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>傳回值  
 已設定之取樣器的篩選模式。  
  
##  <a name="operator_eq"></a>運算子 = 

 將另一個取樣器物件的值指派給現有的取樣器。  
  
```  
sampler& operator= (// [1] copy assignment operator const sampler& _Other) restrict(amp,
    cpu);

 
sampler& operator= (// [2] move assingment operator sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>參數  
 `_Other`  
 [1] 複製指派運算子  
 `sampler`要複製到這個物件`sampler`。  
  
 [2] 移動指派運算子  
 `sampler`物件移至這`sampler`。  
  
### <a name="return-value"></a>傳回值  
 此取樣器執行個體的參考。  
  
## <a name="see-also"></a>另請參閱  
 [Concurrency::graphics 命名空間](concurrency-graphics-namespace.md)
