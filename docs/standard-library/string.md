---
title: '&lt;string&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::<string>
- string/std::<string>
- std.<string>
- <string>
dev_langs:
- C++
helpviewer_keywords:
- string header
ms.assetid: a2fb9d00-d7ae-4170-bfea-2dc337aa37cf
caps.latest.revision: 23
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
ms.openlocfilehash: 6cc4af94f5eae06cde244da58c4aa03e561821a7
ms.contentlocale: zh-tw
ms.lasthandoff: 04/29/2017

---
# <a name="ltstringgt"></a>&lt;string&gt;
定義容器範本類別 `basic_string` 和各種支援的範本。  
  
 如需 `basic_string` 的詳細資訊，請參閱 [basic_string Class](../standard-library/basic-string-class.md)。  
  
## <a name="syntax"></a>語法  
  
```  
#include <string>  
```  
  
## <a name="remarks"></a>備註  
 C++ 語言和 C++ 標準程式庫支援兩種字串類型：  
  
-   以 Null 結束的字元陣列，通常稱為 C 字串。  
  
-   類型 `basic_string` 的範本類別物件，處理所有 `char` 之類的範本引數。  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[string](../standard-library/string-typedefs.md#string)|類型，以類型 `basic_string` 的元素做為 `char`，描述範本類別 `string` 的特製化。|  
|[wstring](../standard-library/string-typedefs.md#wstring)|類型，以類型 `basic_string` 的元素做為 `wchar_t`，描述範本類別 `wstring` 的特製化。|  
|[u16string](../standard-library/string-typedefs.md#u16string)|類型，根據類型 `basic_string` 的元素，描述範本類別 `char16_t` 的特製化。|  
|[u32string](../standard-library/string-typedefs.md#u32string)|類型，根據類型 `basic_string` 的元素，描述範本類別 `char32_t` 的特製化。|  
  
### <a name="operators"></a>運算子  
  
|||  
|-|-|  
|[operator+](../standard-library/string-operators.md#op_add)|串連兩個字串物件。|  
|[operator!=](../standard-library/string-operators.md#op_neq)|測試運算子左邊的字串物件是否不等於右邊的字串物件。|  
|[operator==](../standard-library/string-operators.md#op_eq_eq)|測試運算子左邊的字串物件是否等於右邊的字串物件。|  
|[operator<](../standard-library/string-operators.md#op_lt)|測試運算子左邊的字串物件是否小於右邊的字串物件。|  
|[operator<=](../standard-library/string-operators.md#op_lt_eq)|測試運算子左邊的字串物件是否小於或等於右邊的字串物件。|  
|[operator<\<](../standard-library/string-operators.md#op_lt_lt)|將字串插入至輸出資料流的範本函式。|  
|[operator>](../standard-library/string-operators.md#op_gt)|測試運算子左邊的字串物件是否大於右邊的字串物件。|  
|[operator>=](../standard-library/string-operators.md#op_gt_eq)|測試運算子左邊的字串物件是否大於或等於右邊的字串物件。|  
|[operator>>](../standard-library/string-operators.md#op_gt_gt)|從輸入資料流擷取字串的範本函式。|  
  
### <a name="specialized-template-functions"></a>特製化樣板函式  
  
|||  
|-|-|  
|[swap](../standard-library/string-functions.md#swap)|交換兩個字串的字元陣列。|  
|[stod](../standard-library/string-functions.md#stod)|將字元序列轉換為 `double.`|  
|[stof](../standard-library/string-functions.md#stof)|將字元序列轉換為 `float`。|  
|[stoi](../standard-library/string-functions.md#stoi)|將字元序列轉換為整數。|  
|[stold](../standard-library/string-functions.md#stold)|將字元序列轉換為 `long double`。|  
|[stoll](../standard-library/string-functions.md#stoll)|將字元序列轉換為 `long long`。|  
|[stoul](../standard-library/string-functions.md#stoul)|將字元序列轉換為 `unsigned long`。|  
|[stoull](../standard-library/string-functions.md#stoull)|將字元序列轉換為 `unsigned long long`。|  
|[to_string](../standard-library/string-functions.md#to_string)|將值轉換成 `string`。|  
|[to_wstring](../standard-library/string-functions.md#to_wstring)|將值轉換成寬 `string`。|  
  
### <a name="functions"></a>函式  
  
|||  
|-|-|  
|[getline 範本](../standard-library/string-functions.md#getline)|從輸入資料流一行一行地擷取字串。|  
  
### <a name="classes"></a>類別  
  
|||  
|-|-|  
|[basic_string 類別](../standard-library/basic-string-class.md)|範本類別，描述可以儲存一連串任意類似字元之物件的物件。|  
|[char_traits 結構](../standard-library/char-traits-struct.md)|範本類別，描述與 CharType 類型的字元相關聯的屬性。|  
  
### <a name="specializations"></a>特製化  
  
|||  
|-|-|  
|[char_traits\<char> 結構](../standard-library/char-traits-char-struct.md)|結構，會將樣板結構 `char_traits`\<CharType> 特製化為 `char` 類型的項目。|  
|[char_traits<wchar_t> 結構](../standard-library/char-traits-wchar-t-struct.md)|結構，會將樣板結構 `char_traits`\<CharType> 特製化為 `wchar_t` 類型的項目。|  
|[char_traits<char16_t> 結構](../standard-library/char-traits-char16-t-struct.md)|結構，會將樣板結構 `char_traits`\<CharType> 特製化為 `char16_t` 類型的項目。|  
|[char_traits<char32_t> 結構](../standard-library/char-traits-char32-t-struct.md)|結構，會將樣板結構 `char_traits`\<CharType> 特製化為 `char32_t` 類型的項目。|  
  
## <a name="requirements"></a>需求  
  
- **標頭：**\<string>  
  
- **命名空間：** std  
  
## <a name="see-also"></a>另請參閱  
 [標頭檔參考](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)



