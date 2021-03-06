---
title: CElementTraits 類別
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 4951f5b87efbff83f39badba5f3e1041a15d8c6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480752"
---
# <a name="celementtraits-class"></a>CElementTraits 類別

這個類別的集合類別來移動、 複製、 相較之下，和雜湊作業提供方法和函式。

## <a name="syntax"></a>語法

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>參數

*T*<br/>
若要在集合中儲存的資料型別。

## <a name="remarks"></a>備註

這個類別會提供預設的靜態函式和方法，移動、 複製、 比較及集合類別物件中儲存的雜湊項目。 `CElementTraits` 指定為這些作業的預設提供者的集合類別[CAtlArray](../../atl/reference/catlarray-class.md)， [CAtlList](../../atl/reference/catllist-class.md)， [CRBMap](../../atl/reference/crbmap-class.md)， [CRBMultiMap](../../atl/reference/crbmultimap-class.md)，並[CRBTree](../../atl/reference/crbtree-class.md)。

應可滿足簡單資料類型的預設實作，但集合類別用來儲存更複雜的物件，如果函式和方法必須覆寫使用者所提供的實作。

如需詳細資訊，請參閱 < [ATL 集合類別](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>需求

**標頭：** atlcoll.h

## <a name="see-also"></a>另請參閱

[CDefaultElementTraits 類別](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[類別概觀](../../atl/atl-class-overview.md)
