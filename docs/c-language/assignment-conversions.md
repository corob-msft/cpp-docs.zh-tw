---
title: 指派轉換
ms.date: 11/04/2016
helpviewer_keywords:
- conversions, assignment
- assignment conversions
ms.assetid: 4ee01013-de32-4aae-b12e-0051d0cde927
ms.openlocfilehash: fb3da57af62171ef9670267f94f01ccc097e5942
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649107"
---
# <a name="assignment-conversions"></a>指派轉換

在指派運算中，將指派值的類型會轉換成接收指派的變數類型。 C 可藉由指派而在整數和浮點類型之間轉換，即使資訊會在轉換過程中遺失。 使用的轉換方法取決於指派時採用的類型，如[一般算術轉換](../c-language/usual-arithmetic-conversions.md)與以下各節中所述：

- [從帶正負號整數型別的轉換](../c-language/conversions-from-signed-integral-types.md)

- [從不帶正負號整數型別的轉換](../c-language/conversions-from-unsigned-integral-types.md)

- [從浮點類型的轉換](../c-language/conversions-from-floating-point-types.md)

- [指標類型的轉換](../c-language/conversions-to-and-from-pointer-types.md)

- [從其他類型轉換](../c-language/conversions-from-other-types.md)

類型限定詞不會影響轉換的允許值，雖然 **const** 左值不可以在指派的左邊使用。

## <a name="see-also"></a>請參閱

[類型轉換](../c-language/type-conversions-c.md)