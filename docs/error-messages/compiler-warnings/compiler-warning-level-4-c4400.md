---
title: 編譯器警告 (層級 4) C4400
ms.date: 11/04/2016
f1_keywords:
- C4400
helpviewer_keywords:
- C4400
ms.assetid: f135fe98-4f92-4e07-9d71-2621b36ee755
ms.openlocfilehash: 61a6d3090355c9bda8aa11c041b302e4ec77ec8d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557270"
---
# <a name="compiler-warning-level-4-c4400"></a>編譯器警告 (層級 4) C4400

'type': 不支援此類型的 const/volatile 限定詞

[Const](../../cpp/const-cpp.md)並[volatile](../../cpp/volatile-cpp.md)限定詞不適用於 common language runtime 類型的變數。

## <a name="example"></a>範例

下列範例會產生 C4400。

```
// C4400.cpp
// compile with: /clr /W4
// C4401 expected
using namespace System;
#pragma warning (disable : 4101)
int main() {
   const String^ str;   // C4400
   volatile String^ str2;   // C4400
}
```