---
title: 類別和結構 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++, classes
- structures, C++ classes
- user-defined types
- classes [C++]
- user-defined types, C++ classes
ms.assetid: 516dd496-13fb-4f17-845a-e9ca45437873
ms.openlocfilehash: 44736b9515363d1406b124858f72f12f8f7f552a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562743"
---
# <a name="classes-and-structs-c"></a>類別和結構 (C++)

本節介紹 C++ 類別和結構。 這兩個建構在 C++ 中相同，差異在於結構中的預設存取範圍是公用，而類別中的預設值是私用。

類別和結構是可讓您定義專屬類型的建構。 類別和結構可以同時包含資料成員和成員函式，以讓您描述類型的狀態和行為。

其中包含下列主題：

- [class](../cpp/class-cpp.md)

- [struct](../cpp/struct-cpp.md)

- [類別成員概觀](../cpp/class-member-overview.md)

- [成員存取控制](../cpp/member-access-control-cpp.md)

- [繼承](../cpp/inheritance-cpp.md)

- [靜態成員](../cpp/static-members-cpp.md)

- [使用者定義類型轉換](../cpp/user-defined-type-conversions-cpp.md)

- [可變動資料成員 （mutable 規範）](../cpp/mutable-data-members-cpp.md)

- [巢狀類別宣告](../cpp/nested-class-declarations.md)

- [匿名類別類型](../cpp/anonymous-class-types.md)

- [成員指標](../cpp/pointers-to-members.md)

- [this 指標](../cpp/this-pointer.md)

- [C++ 位元欄位](../cpp/cpp-bit-fields.md)

三個類別類型是結構、類別和等位。 它們使用宣告[結構](../cpp/struct-cpp.md)，[類別](../cpp/class-cpp.md)，並[union](../cpp/unions.md)關鍵字。 下表顯示這三個類別類型的差異。

如需有關等位的詳細資訊，請參閱[等位](../cpp/unions.md)。 如需 managed 的類別和結構的詳細資訊，請參閱[類別和結構](../windows/classes-and-structs-cpp-component-extensions.md)。

### <a name="access-control-and-constraints-of-structures-classes-and-unions"></a>結構、類別和等位的存取控制和條件約束

|結構|類別|等位|
|----------------|-------------|------------|
|類別索引鍵是**結構**|類別索引鍵是**類別**|類別索引鍵是**聯集**|
|預設存取權是 public|預設存取權是 private|預設存取權是 public|
|沒有使用條件約束|沒有使用條件約束|一次只使用一個成員|

## <a name="see-also"></a>另請參閱

[C++ 語言參考](../cpp/cpp-language-reference.md)