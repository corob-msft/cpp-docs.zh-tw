---
title: ctype_byname 類別
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype_byname
helpviewer_keywords:
- ctype_byname class
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
ms.openlocfilehash: d998747045ece765269ddb013b525b8c06fcdf8b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517737"
---
# <a name="ctypebyname-class"></a>ctype_byname 類別

衍生的範本類別，其描述的物件可以作為特定地區設定的 ctype Facet，以啟用字元分類、大小寫字元轉換，以及原生字元集和地區設定所指定字元集之間的轉換。

## <a name="syntax"></a>語法

```cpp
template <class _Elem>
class ctype_byname : public ctype<_Elem>
{
public:
    explicit ctype_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit ctype_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual __CLR_OR_THIS_CALL ~ctype_byname();

};
```

## <a name="remarks"></a>備註

其行為取決於具名地區設定 `_Locname`。 每個建構函式皆會使用 [ctype](../standard-library/ctype-class.md)\<CharType>( `_Refs`) 或與 `ctype<char>` 對等的基底類別來初始化其基底物件。

## <a name="requirements"></a>需求

**標頭︰**\<locale>

**命名空間：** std

## <a name="see-also"></a>另請參閱

[C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
