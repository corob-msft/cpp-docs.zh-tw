---
title: "C 抽象宣告子 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "抽象宣告子"
  - "宣告子, abstract"
ms.assetid: 6a556ad7-0555-421a-aa02-294d77cda8b5
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# C 抽象宣告子
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

抽象宣告子是一個沒有識別項的宣告子，由一個或多個指標、陣列或函式修飾符組成。  指標修飾詞 \(**\***\) 永遠會位於宣告子的識別項之前，陣列 \(**\[ \]**\) 和函式 \( **\( \)** \) 修飾詞會位於識別項的後方。  知道這一點後，您就可以判斷識別項會出現在抽象宣告子的哪個位置，並據以解譯宣告子。  如需複雜宣告子的詳細資訊和範例，請參閱[解譯更複雜的宣告子](../c-language/interpreting-more-complex-declarators.md)。  通常可使用 `typedef` 來簡化宣告子。  請參閱 [Typedef 宣告](../c-language/typedef-declarations.md)。  
  
 抽象宣告子可能很複雜。  複雜抽象宣告子中的括號會指定特定的解譯，就如同在宣告中針對複雜宣告子所做的動作。  
  
 這些範例說明抽象宣告子：  
  
```  
int *         // The type name for a pointer to type int:  
  
int *[3]      // An array of three pointers to int  
  
int (*) [5]   // A pointer to an array of five int  
  
int *()       // A function with no parameter specification  
              // returning a pointer to int  
  
// A pointer to a function taking no arguments and   
// returning an int  
  
int (*) ( void )    
  
// An array of an unspecified number of constant pointers to   
// functions each with one parameter that has type unsigned int   
// and an unspecified number of other parameters returning an int   
  
int (*const []) ( unsigned int, ... )  
```  
  
> [!NOTE]
>  抽象宣告子由一組空括號、**\( \)** 組成，由於會造成模稜兩可的情況，因此不允許使用。  要判斷隱含的識別項是落在括號內部 \(在此情況下它是未經修改的類型\) 或在括號前面 \(在此情況下它是函式類型\) 是不可能的。  
  
## 請參閱  
 [宣告子和變數宣告](../c-language/declarators-and-variable-declarations.md)