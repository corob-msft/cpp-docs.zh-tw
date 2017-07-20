---
title: "exponential_distribution 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- exponential_distribution
- random/std::exponential_distribution
- random/std::exponential_distribution::reset
- random/std::exponential_distribution::lambda
- random/std::exponential_distribution::param
- random/std::exponential_distribution::min
- random/std::exponential_distribution::max
- random/std::exponential_distribution::operator()
- random/std::exponential_distribution::param_type
- random/std::exponential_distribution::param_type::lambda
- random/std::exponential_distribution::param_type::operator==
- random/std::exponential_distribution::param_type::operator!=
- random/std::exponential_distribution::param_type
dev_langs:
- C++
helpviewer_keywords:
- exponential_distribution class
ms.assetid: d54f3126-a09b-45f9-a30b-0d94d03bcdc9
caps.latest.revision: 18
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
ms.openlocfilehash: eaf28ef7a02d358422d7e655688f5f4bf7cccc7d
ms.contentlocale: zh-tw
ms.lasthandoff: 04/29/2017

---
# <a name="exponentialdistribution-class"></a>exponential_distribution 類別
產生指數分佈。  
  
## <a name="syntax"></a>語法  
  
```  
template<class RealType = double>
class exponential_distribution  
   {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   
   // constructors and reset functions  
   explicit exponential_distribution(result_type lambda = 1.0);
   explicit exponential_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   result_type lambda() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
``` 
### <a name="parameters"></a>參數  
*RealType*  
浮點結果類型，預設值為 `double`。 如需可能的類型，請參閱 [\<random>](../standard-library/random.md)。  
  
*URNG* 亂數產生器引擎。 如需可能的類型，請參閱 [\<random>](../standard-library/random.md)。
  
  
## <a name="remarks"></a>備註  
 此範本類別描述產生使用者指定之整數類型的值的分佈 (若無提供則為 `double` 類型)，而這是根據指數分佈進行分佈。 下表提供各個成員的文章連結。  
  
||||  
|-|-|-|  
|[exponential_distribution](#exponential_distribution)|`exponential_distribution::lambda`|`exponential_distribution::param`|  
|`exponential_distribution::operator()`||[param_type](#param_type)|  
  
屬性成員函式 `lambda()` 會傳回預存的分佈參數 `lambda` 值。  
  
屬性成員函式 `param()` 會設定或傳回 `param_type` 預存的分佈參數套件。  
  
如需分佈類別及其成員的詳細資訊，請參閱 [\<random>](../standard-library/random.md)。  
  
如需指數分佈的詳細資訊，請參閱 Wolfram MathWorld 文章 [Exponential Distribution](http://go.microsoft.com/fwlink/LinkId=401098) (指數分佈)。  
  
## <a name="example"></a>範例  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double l, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::exponential_distribution<> distr(l);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "lambda() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.lambda() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<double, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    int counter = 0;  
    for (const auto& elem : histogram) {  
        std::cout << std::fixed << std::setw(11) << ++counter << ": "  
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double l_dist = 0.5;  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): ";  
    std::cin >> l_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(l_dist, samples);  
}  
  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == 0  
max() == 1.79769e+308  
lambda() == 1.0000000000  
Distribution for 10 samples:  
    1: 0.0936880533  
    2: 0.1225944894  
    3: 0.6443593183  
    4: 0.6551171649  
    5: 0.7313457551  
    6: 0.7313557977  
    7: 0.7590097389  
    8: 1.4466885214  
    9: 1.6434088411  
    10: 2.1201210996  
```  
  
## <a name="requirements"></a>需求  
 **標頭：**\<random>  
  
 **命名空間：** std  
  
##  <a name="exponential_distribution"></a>  exponential_distribution::exponential_distribution  
 建構分佈。  
  
```  
explicit exponential_distribution(result_type lambda = 1.0);
explicit exponential_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>參數  
*lambda*  
 `lambda` 分佈參數。  
  
*parm*  
 用於建構分佈的參數封裝。  
  
### <a name="remarks"></a>備註  
**前置條件：**`0.0 < lambda`  
  
第一個建構函式的物件，其預存的 `lambda` 值具有 *lambda* 值。  
  
第二個建構函式建構的物件，其預存參數是從 *parm* 初始化而來。 您可以呼叫 `param()` 成員函式，取得及設定現有分佈的目前參數。  
  
##  <a name="param_type"></a>  exponential_distribution::param_type  
儲存分佈的參數。  
  
```
struct param_type {  
   typedef exponential_distribution<result_type> distribution_type;  
   param_type(result_type lambda = 1.0);
   result_type lambda() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```  
  
### <a name="parameters"></a>參數  
*lambda*  
`lambda` 分佈參數。  
  
*right*  
要與這個項目比較的 `param_type` 物件。  
  
### <a name="remarks"></a>備註  
**前置條件：**`0.0 < lambda`  
  
此結構可在具現化時傳遞至分佈的類別建構函式，傳遞至 `param()` 成員函式可設定現有分佈之儲存的參數，傳遞至 `operator()` 可用於取代儲存的參數。  
  
## <a name="see-also"></a>另請參閱  
[\<random>](../standard-library/random.md)

