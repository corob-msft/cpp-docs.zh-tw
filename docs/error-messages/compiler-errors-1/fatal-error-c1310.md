---
title: 嚴重錯誤 C1310
ms.date: 11/04/2016
f1_keywords:
- C1310
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
ms.openlocfilehash: 1b0fca9a5e453fd354a4efc6960a54386795ccf6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559042"
---
# <a name="fatal-error-c1310"></a>嚴重錯誤 C1310

特性指引最佳化不適用於 OpenMP

您不能使用 [/LTCG:PGI](../../build/reference/ltcg-link-time-code-generation.md) 連結任何以 [/GL](../../build/reference/gl-whole-program-optimization.md)編譯的模組。

下列範例會產生 C1310：

```
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```