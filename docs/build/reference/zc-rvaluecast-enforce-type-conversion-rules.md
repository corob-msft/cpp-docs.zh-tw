---
title: /Zc:rvalueCast (強制型別轉換規則)
ms.date: 03/06/2018
f1_keywords:
- rvaluecast
- /Zc:rvalueCast
- VC.Project.VCCLCompilerTool.EnforceTypeConversionRules
helpviewer_keywords:
- -Zc compiler options (C++)
- rvaluecast
- Enforce type conversion rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
ms.openlocfilehash: 8e4be80d09ebf7f48795e01669610a0dc4f736d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648197"
---
# <a name="zcrvaluecast-enforce-type-conversion-rules"></a>/Zc:rvalueCast (強制型別轉換規則)

當 **/zc: rvaluecast**指定選項時，編譯器正確地識別右值參考類型為根據 C + + 11 標準轉換運算的結果。 當未指定該選項時，編譯器的行為會與 Visual Studio 2012 中的行為相同。

## <a name="syntax"></a>語法

> **/Zc:rvalueCast**[**-**]

## <a name="remarks"></a>備註

如果 **/zc: rvaluecast**指定，則編譯器會遵循 C + + 11 標準的 5.4 節，並視為只轉型運算式導致非參考類型，並轉換導致非函式類型右值參考的運算式右值類型。 根據預設，或如果 **/Zc:rvalueCast-** 指定，則編譯器會不一致，並將導致右值的右值參考的所有轉型運算式。 為了一致性，並消除使用轉型的錯誤，我們建議您使用 **/zc: rvaluecast**。

根據預設， **/zc: rvaluecast**已關閉 (**/Zc:rvalueCast-**)。 [/Permissive--](permissive-standards-conformance.md)編譯器選項會隱含地設定此選項，但可以使用覆寫 **/Zc:rvalueCast-**。

使用 **/zc: rvaluecast**如果您將轉型運算式作為引數傳遞至接受右值參考類型的函式。 預設行為會造成編譯器錯誤[C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md)編譯器錯誤地判定轉型運算式的類型。 此範例顯示在正確的編譯器錯誤程式碼的時機 **/zc: rvaluecast**未指定：

```cpp
// Test of /Zc:rvalueCast
// compile by using:
// cl /c /Zc:rvalueCast- make_thing.cpp
// cl /c /Zc:rvalueCast make_thing.cpp

#include <utility>

template <typename T>
struct Thing {
   // Construct a Thing by using two rvalue reference parameters
   Thing(T&& t1, T&& t2)
      : thing1(t1), thing2(t2) {}

   T& thing1;
   T& thing2;
};

// Create a Thing, using move semantics if possible
template <typename T>
Thing<T> make_thing(T&& t1, T&& t2)
{
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));
}

struct Test1 {
   long a;
   long b;

   Thing<long> test() {
      // Use identity casts to create rvalues as arguments
      return make_thing(static_cast<long>(a), static_cast<long>(b));
   }
};
```

適當時，預設編譯器行為可能不會報告錯誤 C2102。 在此範例中，編譯器不會報告錯誤採用身分轉型所建立之右值的位址時，如果 **/zc: rvaluecast**未指定：

```cpp
int main() {
   int a = 1;
   int *p = &a;   // Okay, take address of lvalue
                  // Identity cast creates rvalue from lvalue;
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value
}
```

如需 Visual C++ 中一致性問題的詳細資訊，請參閱 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資料，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 選取 **組態屬性** > **C/c + +** > **命令列**屬性頁。

1. 修改**其他選項**屬性，以包括 **/zc: rvaluecast** ，然後選擇**確定**。

## <a name="see-also"></a>另請參閱

[/Zc (一致性)](../../build/reference/zc-conformance.md)<br/>
