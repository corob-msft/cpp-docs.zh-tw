---
title: "C 常數運算式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: d48a6c47-e44c-4be2-9c8b-7944c7ef8de7
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 0e3323c85ce7668adfe5b4a297ac8bab930c3ae6
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="c-constant-expressions"></a>C 常數運算式
常數運算式會在編譯時期評估，而不是在執行階段評估，而且可用於可以使用常數的任何位置。 常數運算式必須評估為常數，並且必須在該類型可顯示值的範圍內。 常數運算式的運算元可以是整數常數、字元常數、浮點常數、列舉常數、類型轉換、`sizeof` 運算式和其他常數運算式。  
  
## <a name="syntax"></a>語法  
 *constant-expression*：  
 *conditional-expression*  
  
 *conditional-expression*：  
 *logical-OR-expression*  
  
 *logical-OR-expression* **?**  *expression* **:**  *conditional-expression*  
  
 *expression*：  
 *assignment-expression*  
  
 *expression* **,**  *assignment-expression*  
  
 *assignment-expression*：  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*：下列其中一個  
 **= \*= /= %= += -= <\<= >>= &= ^= &#124;=**  
  
 結構宣告子、列舉程式、直接宣告子、直接抽象宣告子和標記陳述式包含 *constant-expression* 非終端項。  
  
 必須使用整數常數運算式指定結構的位元欄位成員、列舉常數的值、陣列的大小或 **case** 常數的值。  
  
 前置處理器指示詞中所使用的常數運算式必須遵守其他限制。 因此，這些運算式稱為「受限制的常數運算式」。 受限制的常數運算式不能包含 `sizeof` 運算式、列舉常數、任何類型的類型轉換，或浮點類型常數。 不過，此類運算式可以包含特殊常數運算式 `defined (`*identifier*`)`。  
  
## <a name="see-also"></a>另請參閱  
 [運算元和運算式](../c-language/operands-and-expressions.md)