---
title: 編譯器錯誤 C2714
ms.date: 11/04/2016
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: feba363a7cd15d92bf850e8cba457ff310d15490
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556360"
---
# <a name="compiler-error-c2714"></a>編譯器錯誤 C2714

不允許 __alignof(void)

無效的值傳遞給操作員。

請參閱[__alignof 運算子](../../cpp/alignof-operator.md)如需詳細資訊。

## <a name="example"></a>範例

下列範例會產生 C2714。

```
// C2714.cpp
int main() {
   return __alignof(void);   // C2714
   return __alignof(char);   // OK
}
```