---
title: '&lt;codecvt&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt
- std::<codecvt>
- std.<codecvt>
- <codecvt>
dev_langs:
- C++
helpviewer_keywords:
- codecvt header
ms.assetid: d44ee229-00d5-4761-9b48-0c702122789d
caps.latest.revision: 21
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
ms.sourcegitcommit: 86978cd4549f0672dac7cad0e4713380ea189c27
ms.openlocfilehash: 75f527ca1e0742a1958076b49446b257793c69a5
ms.contentlocale: zh-tw
ms.lasthandoff: 04/18/2017

---
# <a name="ltcodecvtgt"></a>&lt;codecvt&gt;
定義數個範本類別，以依據 [codecvt](../standard-library/codecvt-class.md) 範本類別描述物件。 這些物件可以作為[地區設定 Facet](../standard-library/locale-class.md#facet_class)，以控制 `Elem` 類型的值序列和 `char` 類型的值序列之間的轉換。  
  
## <a name="syntax"></a>語法  
  
```  
#include <codecvt>  
  
```  
  
## <a name="remarks"></a>備註  
 此標頭中宣告的地區設定 Facet 可在數種字元編碼之間進行轉換。 若是寬字元 (以固定大小的整數形式儲存在程式內)︰  
  
-   UCS-4 會在程式內以 Unicode (ISO 10646) 編碼。  
  
-   UCS-4 會在程式內以 Unicode (ISO 10646) 編碼為 32 位元整數。  
  
-   UCS-2 會在程式內以 Unicode 編碼。  
  
-   UCS-2 會在程式內以 Unicode 編碼為 16 位元整數。  
  
-   UTF-16 會在程式內以 Unicode 編碼為任一整數。  
  
-   UTF-16 會在程式內以 Unicode 編碼為一個或兩個 16 位元整數。 (請注意，這並不符合標準 C 或標準 C++ 有效寬字元編碼的所有需求， 但這卻是廣泛使用的情況)。  
  
 若是位元組資料流 (儲存在檔案、以位元組序列傳輸，或儲存在 `char` 陣列中的程式內)：  
  
-   UTF-8 會以 Unicode 編碼。  
  
-   UTF-8 會在位元組資料流內以 Unicode 編碼為一或多個 8 位元位元組 (按具決定性的位元組順序)。  
  
-   UTF-16LE 會以 Unicode 編碼。  
  
-   UTF-16LE 會在位元組資料流內以 Unicode 編碼為 UTF-16 (其中每個 16 位元整數會顯示為兩個 8 位元位元組，較不顯著的位元組在前)。  
  
-   UTF-16BE 會以 Unicode 編碼。  
  
-   UTF-16BE 會在位元組資料流內以 Unicode 編碼為 UTF-16 (其中每個 16 位元整數會顯示為兩個 8 位元位元組，較顯著的位元組在前)。  
  
### <a name="enumerations"></a>列舉  
  
|||  
|-|-|  
|[codecvt_mode](../standard-library/codecvt-enums.md#codecvt_mode)|指定地區設定 Facet 的設定資訊。|  
  
### <a name="classes"></a>類別  
  
|||  
|-|-|  
|[codecvt_utf8](codecvt-utf8-class.md)|代表地區設定 Facet，其可在 UCS-2 或 UCS-4 編碼的寬字元以及 UTF-8 編碼的位元組資料流之間進行轉換。|  
|[codecvt_utf8_utf16](codecvt-utf8-utf16-class.md)|代表地區設定 Facet，其可在 UTF-16 編碼的寬字元以及 UTF-8 編碼的位元組資料流之間進行轉換。|  
|[codecvt_utf16](codecvt-utf16-class.md)|代表地區設定 Facet，其可在 UCS-2 或 UCS-4 編碼的寬字元以及 UTF-16LE 或 UTF-16BE 編碼的位元組資料流之間進行轉換。|  

  
## <a name="requirements"></a>需求  
 **標頭：**\<codecvt>  
  
 **命名空間：**stdt  
  
## <a name="see-also"></a>另請參閱  
 [標頭檔參考](../standard-library/cpp-standard-library-header-files.md)




