---
title: 編譯器錯誤 C3482
ms.date: 11/04/2016
f1_keywords:
- C3482
helpviewer_keywords:
- C3482
ms.assetid: bf99558e-bef4-421c-bb16-dcd9c54c1011
ms.openlocfilehash: ec0018fc1aafc7e3e0423608f4db9f78946e4597
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432629"
---
# <a name="compiler-error-c3482"></a>編譯器錯誤 C3482

'this' 在非靜態成員函式內只能做為 Lambda 擷取

您無法將 `this` 傳遞給靜態方法或全域函式中所宣告之 Lambda 運算式的擷取清單。

### <a name="to-correct-this-error"></a>更正這個錯誤

- 將封入函式轉換成非靜態方法，或

- 從 Lambda 運算式的擷取清單中移除 `this` 指標。

## <a name="example"></a>範例

下列範例會產生 C3482：

```
// C3482.cpp
// compile with: /c

class C
{
public:
   static void staticMethod()
   {
      [this] {}(); // C3482
   }
};
```

## <a name="see-also"></a>另請參閱

[Lambda 運算式](../../cpp/lambda-expressions-in-cpp.md)