---
title: 連結器工具錯誤 LNK1301
ms.date: 11/04/2016
f1_keywords:
- LNK1301
helpviewer_keywords:
- LNK1301
ms.assetid: 760da428-7182-4b25-b20a-de90d4b9a9cd
ms.openlocfilehash: b112c4498913c18d82ce8fbc4f6c6d211b906263
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431235"
---
# <a name="linker-tools-error-lnk1301"></a>連結器工具錯誤 LNK1301

找不到，/LTCG:parameter 與不相容的 LTCG clr 模組

以 /clr 和 /GL 編譯的模組已傳遞給連結器，以及其中一個特性指引最佳化 (PGO) 參數 /LTCG。

/Clr 模組不支援特性指引最佳化。

如需詳細資訊，請參閱:

- [/GL (整個程式最佳化)](../../build/reference/gl-whole-program-optimization.md)

- [/LTCG (連結時間產生程式碼)](../../build/reference/ltcg-link-time-code-generation.md)

- [/clr (通用語言執行平台編譯)](../../build/reference/clr-common-language-runtime-compilation.md)

- [特性指引最佳化](../../build/reference/profile-guided-optimizations.md)

### <a name="to-correct-this-error"></a>更正這個錯誤

1. 不使用 /clr 編譯，或沒有與 /LTCG 的 PGO 參數的其中一個連結。

## <a name="example"></a>範例

下列範例會產生 LNK1301:

```
// LNK1301.cpp
// compile with: /clr /GL /link /LTCG:PGI LNK1301.obj
// LNK1301 expected
class MyClass {
public:
   int i;
};
```