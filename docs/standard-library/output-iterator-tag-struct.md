---
title: output_iterator_tag 結構
ms.date: 11/04/2016
f1_keywords:
- xutility/std::output_iterator_tag
helpviewer_keywords:
- output_iterator_tag class
- output_iterator_tag struct
ms.assetid: c23a4331-b069-4fa0-9c3a-1c9be7095553
ms.openlocfilehash: cb2a59d2c81e6d7cc80de2714ba86476c5fa837f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659300"
---
# <a name="outputiteratortag-struct"></a>output_iterator_tag 結構

這個類別提供的傳回型別`iterator_category`表示輸出迭代器函式。

## <a name="syntax"></a>語法

output_iterator_tag 結構{};

## <a name="remarks"></a>備註

分類標籤類別會用來當作可供選取演算法的編譯標籤。 範本函式必須尋找其迭代器引數的最明確分類，如此它才能在編譯階段使用最有效率的演算法。 對於 `Iterator` 類型的每個迭代器，必須將 `iterator_traits`< `Iterator`> **::iterator_category** 定義為描述迭代器行為最精確的分類標籤。

型別是相同**迭代器**\< **Iter**> **:: iterator_category**時`Iter`描述可以做為物件輸出迭代器。

如同其他的迭代器標籤，此標籤並未在迭代器的 `value_type` 或 `difference_type` 上參數化，因為輸出迭代器並不具有 `value_type` 或 `difference_type`。

## <a name="example"></a>範例

請參閱[iterator_traits](../standard-library/iterator-traits-struct.md)或是[random_access_iterator_tag](../standard-library/random-access-iterator-tag-struct.md)如需如何使用的範例`iterator_tag`s。

## <a name="requirements"></a>需求

**標頭：**\<iterator>

**命名空間：** std

## <a name="see-also"></a>另請參閱

[C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ 標準程式庫參考](../standard-library/cpp-standard-library-reference.md)<br/>
