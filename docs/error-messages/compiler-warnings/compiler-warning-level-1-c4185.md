---
title: 編譯器警告 (層級 1) C4185
ms.date: 11/04/2016
f1_keywords:
- C4185
helpviewer_keywords:
- C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
ms.openlocfilehash: c4cabeb206da8da9f9157a8f8eee65c1894ce024
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475110"
---
# <a name="compiler-warning-level-1-c4185"></a>編譯器警告 (層級 1) C4185

忽略未知的 #import 屬性 'attribute'

屬性不是 `#import`的有效屬性。 會忽略此項。

## <a name="example"></a>範例

```
// C4185.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_such_attribute   // C4185
```