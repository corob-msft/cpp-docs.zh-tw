---
title: 編譯器錯誤 C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 9d9ba48b0607e7a30b8748d4e9ae4f7025f11dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50522989"
---
# <a name="compiler-error-c2511"></a>編譯器錯誤 C2511

'identifier': 多載 'class' 中找不到成員函式

任何版本的函式會使用指定的參數不宣告。  可能的原因：

1. 錯誤的參數傳遞至函式。

1. 參數傳遞錯誤的順序。

1. 參數名稱的拼字錯誤。

下列範例會產生 C2511:

```
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```