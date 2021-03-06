---
title: 實作 CComObject、 CComAggObject 和 CComPolyObject
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: 6e9e1a22ebe23f9fec6e553713a5701315cdac96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508975"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>實作 CComObject、 CComAggObject 和 CComPolyObject

範本類別[CComObject](../atl/reference/ccomobject-class.md)， [CComAggObject](../atl/reference/ccomaggobject-class.md)，並[CComPolyObject](../atl/reference/ccompolyobject-class.md)一律會繼承鏈結中的最具衍生性的類別。 其須負責處理的方法中的所有`IUnknown`: `QueryInterface`， `AddRef`，和`Release`。 颾魤 ㄛ`CComAggObject`並`CComPolyObject`（使用彙總的物件） 時提供特殊的參考計數和`QueryInterface`所需的內部未知的語意。

是否`CComObject`， `CComAggObject`，或`CComPolyObject`用取決於您宣告一個 （或無） 下列巨集：

|巨集|作用|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|一律會使用`CComObject`。|
|DECLARE_AGGREGATABLE|會使用`CComAggObject`如果已彙總物件和`CComObject`如果不是。 `CComCoClass` 包含此巨集，如果沒有 DECLARE_ * _AGGREGATABLE 巨集是在類別中宣告，這是預設值。|
|DECLARE_ONLY_AGGREGATABLE|一律會使用`CComAggObject`。 如果物件不會彙總，會傳回錯誤。|
|DECLARE_POLY_AGGREGATABLE|ATL 建立的執行個體**CComPolyObject\<CYourClass >** 當`IClassFactory::CreateInstance`呼叫。 在建立期間，會檢查的外部未知的值。 如果它是 NULL，`IUnknown`實作非彙總的物件。 如果不是 NULL，外部未知`IUnknown`會彙總物件的實作。|

使用的優點`CComAggObject`並`CComObject`的實作`IUnknown`最適合用於建立物件的類型。 比方說，非彙總的物件只需要一個參考計數，而彙總的物件需要的內部的未知參考計數和外部未知的指標。

使用的優點`CComPolyObject`避免擁有`CComAggObject`和`CComObject`處理彙總及非彙總的情況下在模組中。 單一`CComPolyObject`物件會處理這兩種情況。 這表示只有一個複本的 vtable 和一份函式存在於您的模組。 如果您的 vtable 很大，這可以大幅降低您的模組大小。 不過，如果您的 vtable 很小，使用`CComPolyObject`可能會導致稍微大一點的模組大小因為它不會最佳化彙總或非彙總物件，因為`CComAggObject`和`CComObject`。

## <a name="see-also"></a>另請參閱

[ATL COM 物件的基本概念](../atl/fundamentals-of-atl-com-objects.md)<br/>
[彙總和 Class Factory 巨集](../atl/reference/aggregation-and-class-factory-macros.md)

