---
title: "&lt;chrono&gt; 函式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 68c68070265c8cc7ff4d6c5c070b4e7849d50a91
ms.contentlocale: zh-tw
ms.lasthandoff: 04/19/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt; 函式
||||  
|-|-|-|  
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|  
  

##  <a name="duration_cast"></a>duration_cast
 將 `duration` 物件轉換為指定的類型。  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>傳回值  
 `To` 類型的 `duration` 物件，代表時間間隔 `Dur`，如果必須符合目標類型則會截斷。  
  
### <a name="remarks"></a>備註  
 如果 `To` 是 `duration` 的具現化，此函式不會參與多載解析。  
  
##  <a name="time_point_cast"></a>time_point_cast
 將 [time_point](../standard-library/time-point-class.md) 物件轉換為指定的類型。  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>傳回值  
 具有 `To` 類型之持續時間的 `time_point` 物件。  
  
### <a name="remarks"></a>備註  
 除非 `To` 是 [duration](../standard-library/duration-class.md) 的具現化，否則此函式不會參與多載解析。  
  
## <a name="see-also"></a>另請參閱  
 [\<chrono>](../standard-library/chrono.md)

