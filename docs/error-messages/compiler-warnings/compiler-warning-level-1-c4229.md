---
title: 編譯器警告 (層級 1) C4229
ms.date: 11/04/2016
f1_keywords:
- C4229
helpviewer_keywords:
- C4229
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
ms.openlocfilehash: 05d11a02d3aea8748a2955dff77a0af750ee0275
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575535"
---
# <a name="compiler-warning-level-1-c4229"></a>編譯器警告 (層級 1) C4229

過時的用法： 修飾詞，資料會被忽略

使用 Microsoft 修飾詞，例如`__cdecl`資料宣告為過時的作法。

## <a name="example"></a>範例

```
// C4229.cpp
// compile with: /W1 /LD
int __cdecl counter;   // C4229 cdecl ignored
```