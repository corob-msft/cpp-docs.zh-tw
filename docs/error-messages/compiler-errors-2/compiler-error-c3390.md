---
title: "編譯器錯誤 C3390 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3390
dev_langs:
- C++
helpviewer_keywords:
- C3390
ms.assetid: 84800a87-c8e6-45aa-82ae-02f816dc8d97
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: 257b0678ded15815f6673091d1adb26dea1dec12
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3390"></a>編譯器錯誤 C3390
'type_arg' : 對泛型參數 'param' (屬於泛型 'generic_type') 無效的類型引數，必須是參考類型  
  
泛型類型未正確地具現化。  請檢查類型定義。  如需詳細資訊，請參閱[泛型](../../windows/generics-cpp-component-extensions.md)。  
  
## <a name="example"></a>範例  
第一個範例會使用 C# 建立元件，其中包含已撰寫 C + 中的泛型型別時，不支援某些條件約束的泛型型別 + CLR。 如需詳細資訊，請參閱[型別參數的條件約束](/dotnet/articles/csharp/programming-guide/generics/constraints-on-type-parameters)。  
  
```cs  
// C3390.cs  
// Compile by using: csc /target:library C3390.cs  
// a C# program  
public class GR<C, V, N>  
where C : class  
where V : struct  
where N : new() {}  
```  
  
C3390.dll 元件可用時，下列範例會產生 C3390。  
  
```cpp  
// C3390_b.cpp  
// Compile by using: cl /clr C3390_b.cpp
#using <C3390.dll>  
ref class R { R(int) {} };  
value class V {};  
ref struct N { N() {} };  
  
int main () {  
   GR<V, V, N^>^ gr2;   // C3390 first type must be a ref type  
   GR<R^, V, N^>^ gr2b; // OK  
}  
```