---
title: 編譯器錯誤 C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: f18819e5f078cb85121160af1d4a3fc24a365a68
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615185"
---
# <a name="compiler-error-c2601"></a>編譯器錯誤 C2601

'function': 區域函式定義不合法

程式碼會嘗試定義內的函式的函式。

或者，您也可以在 C2601 錯誤的位置之前的原始程式碼中可能有額外的括號。

下列範例會產生 C2601:

```
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```