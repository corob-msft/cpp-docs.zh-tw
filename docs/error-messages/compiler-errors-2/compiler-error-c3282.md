---
title: 編譯器錯誤 C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 7092ddc3bf6859212cbb143572de1ef3604a13d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491503"
---
# <a name="compiler-error-c3282"></a>編譯器錯誤 C3282

泛型參數清單只能出現在受管理或 WinRTclasses、 結構或函式

使用泛型參數清單的方式錯誤。  如需詳細資訊，請參閱[泛型](../../windows/generics-cpp-component-extensions.md)。

## <a name="example"></a>範例

下列範例會產生 C3282，並示範如何修正此問題。

```
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```