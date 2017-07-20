---
title: "time_point 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
dev_langs:
- C++
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
caps.latest.revision: 10
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 1c4d02cf83401e6a6dce3fa079d43dea0fce6270
ms.contentlocale: zh-tw
ms.lasthandoff: 04/29/2017

---
# <a name="timepoint-class"></a>time_point 類別
`time_point` 描述可代表時間點的類型。 其會保留類型 [duration](../standard-library/duration-class.md) 的物件，儲存自樣板引數 `Clock` 所表示的 epoch 之後的已耗用時間。  
  
## <a name="syntax"></a>語法  
  
```  
template <class Clock,  
    class Duration = typename Clock::duration>  
class time_point;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-typedefs"></a>公用 Typedefs  
  
|名稱|說明|  
|----------|-----------------|  
|`time_point::clock`|`Clock` 樣板參數的同義字。|  
|`time_point::duration`|`Duration` 樣板參數的同義字。|  
|`time_point::period`|巢狀型別名稱的同義字 `duration::period`。|  
|`time_point::rep`|巢狀型別名稱的同義字 `duration::rep`。|  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[time_point](#time_point)|建構 `time_point` 物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[max](#max)|指定 `time_point::ref` 的上限。|  
|[min](#min)|指定 `time_point::ref` 的下限。|  
|[time_since_epoch](#time_since_epoch)|傳回儲存的 `duration` 值。|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|描述|  
|----------|-----------------|  
|[time_point::operator+=](#op_add_eq)|將指定的值加入至預存的 duration 值。|  
|[time_point::operator-=](#operator-_eq)|從預存的 duration 值減去指定的值。|  
  
## <a name="requirements"></a>需求  
 **標頭︰** \<chrono >  
  
 **命名空間：**std::chrono  
  
##  <a name="max"></a>time_point:: max
 靜態方法會傳回型別 `time_point::ref` 的上限值。  
  
```  
static constexpr time_point max();
```  
  
### <a name="return-value"></a>傳回值  
 實際上，系統會傳回 `time_point(duration::max())`。  
  
##  <a name="min"></a>time_point:: min
 靜態方法會傳回型別 `time_point::ref` 的下限值。  
  
```  
static constexpr time_point min();
```  
  
### <a name="return-value"></a>傳回值  
 實際上，系統會傳回 `time_point(duration::min())`。  
  
##  <a name="op_add_eq"></a>  time_point::operator+=  
 將指定的值加入至預存的 [duration](../standard-library/duration-class.md) 值。  
  
```  
time_point& operator+=(const duration& Dur);
```  
  
### <a name="parameters"></a>參數  
 `Dur`  
 `duration` 物件。  
  
### <a name="return-value"></a>傳回值  
 執行加法之後的 `time_point` 物件。  
  
##  <a name="time_point__operator-_eq"></a>  time_point::operator-=  
 從預存的 [duration](../standard-library/duration-class.md) 值減去指定的值。  
  
```  
time_point& operator-=(const duration& Dur);
```  
  
### <a name="parameters"></a>參數  
 `Dur`  
 `duration` 物件。  
  
### <a name="return-value"></a>傳回值  
 執行減法之後的 `time_point` 物件。  
  
##  <a name="time_point"></a>  time_point::time_point 建構函式  
 建構 `time_point` 物件。  
  
```  
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>  
constexpr time_point(const time_point<clock, Duration2>& Tp);
```  
  
### <a name="parameters"></a>參數  
 `Dur`  
 [duration](../standard-library/duration-class.md) 物件。  
  
 `Tp`  
 `time_point` 物件。  
  
### <a name="remarks"></a>備註  
 第一個建構函式會建構預存 `duration` 值等於 [duration::zero](../standard-library/duration-class.md#zero) 的物件。  
  
 第二個建構函式會建構預存持續時間值等於 `Dur` 的物件。 除非 `is_convertible<Duration2, duration>`「判斷為 true」(holds true)，否則第二個建構函式不會參與多載解析。 如需詳細資訊，請參閱 [<type_traits>](../standard-library/type-traits.md)。  
  
 第三個建構函式會使用 `Tp.time_since_epoch()` 初始化其 `duration` 值。  
  
##  <a name="time_since_epoch"></a>time_point:: time_since_epoch
 擷取預存的[duration](../standard-library/duration-class.md) 值。  
  
```  
constexpr duration time_since_epoch() const;
```  
  
## <a name="see-also"></a>另請參閱  
 [標頭檔參考](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)

