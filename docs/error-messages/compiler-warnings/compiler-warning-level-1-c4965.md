---
title: 編譯器警告 (層級 1) C4965
ms.date: 11/04/2016
f1_keywords:
- C4965
helpviewer_keywords:
- C4965
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
ms.openlocfilehash: 7d77df395d680b467d1a04a3f59c9822842f99f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653098"
---
# <a name="compiler-warning-level-1-c4965"></a>編譯器警告 (層級 1) C4965

整數 0; 的隱含 box請使用 nullptr 或明確轉換

Visual c + + 提供隱含 boxing 處理實值型別。 使用 Managed Extensions for c + + 現在已成為 boxed int 指派 null 指派會導致指令

如需詳細資訊，請參閱 [Boxing](../../windows/boxing-cpp-component-extensions.md)中定義的介面的私用 C++ 專屬實作。

## <a name="example"></a>範例

下列範例會產生 C4965。

```
// C4965.cpp
// compile with: /clr /W1
int main() {
   System::Object ^o = 0;   // C4965

   // the previous line is the same as the following line
   // using Managed Extensions for C++
   // System::Object *o = __box(0);

   // OK
   System::Object ^o2 = nullptr;
   System::Object ^o3 = safe_cast<System::Object^>(0);
}
```