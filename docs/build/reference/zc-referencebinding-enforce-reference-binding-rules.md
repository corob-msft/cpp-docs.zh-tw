---
title: "/Zc:referenceBinding （強制執行參考繫結規則） |Microsoft 文件"
ms.custom: 
ms.date: 12/13/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- referenceBinding
- /Zc:referenceBinding
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- referenceBinding
- Enforce reference binding rules
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 0c6cfaac-9c2a-41a3-aa94-64ca8ef261fc
caps.latest.revision: "1"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0d3d352394b61f95e083a2e6e6f0d888fe210b37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="zcreferencebinding-enforce-reference-binding-rules"></a>/Zc:referenceBinding （強制執行參考繫結規則）
當**/Zc:referenceBinding**指定選項時，編譯器不允許非 const 左值參考繫結至暫存。  
  
## <a name="syntax"></a>語法  
  
```  
/Zc:referenceBinding[-]  
```  
  
## <a name="remarks"></a>備註  
如果**/Zc:referenceBinding**指定，則編譯器會遵循 C + + 11 標準 8.5.3 區段，且不允許繫結至非 const 左值參考的暫存使用者定義類型的運算式。 根據預設，或者如果**/Zc:referenceBinding-**指定時，編譯器允許這類運算式做為 Microsoft 擴充功能，但會發出層級 4 警告。 程式碼安全性、 可攜性和一致性，我們建議您使用**/Zc:referenceBinding**。 [/ 寬鬆-](permissive-standards-conformance.md)編譯器選項會隱含地設定此選項，但可以使用覆寫**/Zc:referenceBinding-**。  
  
## <a name="example"></a>範例  
  
這個範例會示範 Microsoft 擴充功能，可讓使用者定義型別的繫結至非 const 左值參考的暫存。
```cpp  
// zcreferencebinding.cpp
struct S {
};

void f(S&) {
}

S g() {
    return S{};
}

void main() {
    S& s = g();         // warning C4239 at /W4
    const S& cs = g();  // okay, bound to const ref
    f(g());             // Extension: error C2664 only if /Zc:referenceBinding
}
```  
  
如需 Visual C++ 中一致性問題的詳細資訊，請參閱 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項  
  
1.  開啟專案的 [屬性頁]  對話方塊。 如需詳細資訊，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。  
  
2.  選取**C/c + +**資料夾。  
  
3.  選取**命令列**屬性頁。  
  
4.  修改**其他選項**屬性，以包括**/Zc:referenceBinding** ，然後選擇 **確定**。  
  
## <a name="see-also"></a>請參閱  
[編譯器選項](../../build/reference/compiler-options.md)   
[設定編譯器選項](../../build/reference/setting-compiler-options.md)   
[/Zc （一致性）](../../build/reference/zc-conformance.md)