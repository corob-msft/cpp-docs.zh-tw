---
title: "chrono 常值 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 1a9e23b1-256f-4570-8226-5fa7364fb032
caps.latest.revision: 10
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 493b622bf49ddd148e0877b15659e10646f46d4e
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="chrono-literals"></a>chrono 常值
(C++14) \<chrono> 標頭定義 12 個[使用者定義常值](../cpp/user-defined-literals-cpp.md)，來加速使用代表小時、分鐘、秒、毫秒、百萬分之一秒及奈秒的常值。 每個使用者定義常值皆有整數和浮點多載。 常值在 literals::chrono_literals 內嵌命名空間中定義，當 std::chrono 在範圍中時會自動將此內嵌命名空間帶入範圍內。  
  
## <a name="syntax"></a>語法  
  
```  
inline namespace literals {  
    inline namespace chrono_literals {  
 // return integral hours  
    constexpr chrono::hours operator"" h(unsigned long long Val);

 // return floating-point hours  
    constexpr chrono::duration<double, ratio<3600>> operator"" h(long double Val);

 // return integral minutes  
    constexpr chrono::minutes(operator"" min)(unsigned long long Val);

 // return floating-point minutes  
    constexpr chrono::duration<double, ratio<60>>(operator"" min)(long double Val);

 // return integral seconds  
    constexpr chrono::seconds operator"" s(unsigned long long Val);

 // return floating-point seconds  
    constexpr chrono::duration<double> operator"" s(long double Val);

 // return integral milliseconds  
    constexpr chrono::milliseconds operator"" ms(unsigned long long Val);

 // return floating-point milliseconds  
    constexpr chrono::duration<double, milli> operator"" ms(long double Val);

 // return integral microseconds      
    constexpr chrono::microseconds operator"" us(unsigned long long Val);

 // return floating-point microseconds  
    inline constexpr chrono::duration<double, micro> operator"" us(long double Val);

 // return integral nanoseconds  
    inline constexpr chrono::nanoseconds operator"" ns(unsigned long long Val);

 // return floating-point nanoseconds  
    constexpr chrono::duration<double, nano> operator"" ns(long double Val);

 }// inline namespace chrono_literals  
}// inline namespace literals  
```  
  
## <a name="return-value"></a>傳回值  
 接受 `long long` 引數的常值會傳回值或對應類型。 接受浮點引數的常值會傳回 [duration](../standard-library/duration-class.md)。  
  
## <a name="example"></a>範例  
 下列範例顯示如何使用 chrono 常值。  
  
```cpp  
constexpr auto day = 24h;  
constexpr auto week = 24h* 7;  
constexpr auto my_duration_unit = 108ms;  
```  
  
## <a name="requirements"></a>需求  
 **標頭**：\<chrono>  
  
 **命名空間**：std::literals::chrono_literals  
  
## <a name="see-also"></a>另請參閱  
 [\<chrono>](../standard-library/chrono.md)

