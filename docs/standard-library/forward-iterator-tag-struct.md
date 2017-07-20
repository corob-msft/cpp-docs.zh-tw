---
title: "forward_iterator_tag 結構 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- forward_iterator_tag
- xutility/std::forward_iterator_tag
dev_langs:
- C++
helpviewer_keywords:
- forward_iterator_tag struct
- forward_iterator_tag class
ms.assetid: 68b633ac-b135-4e9e-837d-14248a262ec5
caps.latest.revision: 20
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 659ada41e69a0d9d2ab90e80b60ea0b3e4546d3b
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="forwarditeratortag-struct"></a>forward_iterator_tag 結構
此類別可提供 **iterator_category** 函式 (其表示正向迭代器) 的傳回類型。  
  
## <a name="syntax"></a>語法  
  
```
struct forward_iterator_tag    : public input_iterator_tag {};
```  
  
## <a name="remarks"></a>備註  
 分類標籤類別會用來當作演算法選擇的編譯標籤。 範本函式必須找出其迭代器引數最精確的分類，在編譯時間才能使用最有效率的演算法。 對於 `Iterator` 類型的每個迭代器，必須將 `iterator_traits`< `Iterator`> **::iterator_category** 定義為描述迭代器行為最精確的分類標籤。  
  
 當 **Iter** 描述的物件可當作正向迭代器時，此類型與 **iterator**\< **Iter**> **::iterator_category** 相同。  
  
## <a name="example"></a>範例  
 如需如何使用 **iterator_tags** 的範例，請參閱 [iterator_traits](../standard-library/iterator-traits-struct.md) 或 [random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)。  
  
## <a name="requirements"></a>需求  
 **標頭：**\<iterator>  
  
 **命名空間：** std  
  
## <a name="see-also"></a>另請參閱  
 [input_iterator_tag 結構](../standard-library/input-iterator-tag-struct.md)   
 [C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準程式庫參考](../standard-library/cpp-standard-library-reference.md)



