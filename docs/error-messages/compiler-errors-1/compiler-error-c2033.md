---
title: 編譯器錯誤 C2033
ms.date: 11/04/2016
f1_keywords:
- C2033
helpviewer_keywords:
- C2033
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
ms.openlocfilehash: 8147c707c70e6c3f21ed81b2acf0a59b72065408
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480427"
---
# <a name="compiler-error-c2033"></a>編譯器錯誤 C2033

'identifier': 位元欄位無法間接取值

位元欄位已宣告為指標，這是不允許的做法。

下列範例會產生 C2033：

```
// C2033.cpp
struct S {
   int *b : 1;  // C2033
};
```

可能的解決方式：

```
// C2033b.cpp
// compile with: /c
struct S {
   int b : 1;
};
```