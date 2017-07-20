---
title: "主要運算式 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "運算式 [C++], 常值"
  - "運算式 [C++], name"
  - "運算式 [C++], 主要"
  - "運算式 [C++], 完整名稱"
  - "主要運算式"
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 主要運算式
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

主要運算式為更複雜運算式的建置組塊。  它們是常值、名稱，以及範圍解析運算子 \(`::`\) 所限定的名稱。主要運算式可以具有下列任何形式：  
  
```  
  
        literal  
this  
:: name  
name   
( expression )  
```  
  
 *literal* 是常數主要運算式。  它的類型取決於其規格形式。  如需有關指定常值的完整資訊，請參閱[常值](../cpp/numeric-boolean-and-pointer-literals-cpp.md)。  
  
 **this** 關鍵字是類別物件的指標。  它可在非靜態成員函式中使用，並且指向針對其叫用函式的類別執行個體。  **this** 關鍵字無法在類別成員函式的主體之外使用。  
  
 **this** 指標的類型在未具體修改 **this** 指標的函式內為 `type` **\*const** \(其中 `type` 是類別名稱\)。  下列範例將示範成員函式宣告和 **this** 的類型：  
  
```  
// expre_Primary_Expressions.cpp  
// compile with: /LD  
class Example  
{  
public:  
    void Func();          //  * const this  
    void Func() const;    //  const * const this  
    void Func() volatile; //  volatile * const this  
};  
```  
  
 如需修改 **this** 指標類型的詳細資訊，請參閱 [this 指標的類型](../misc/type-of-this-pointer.md)。  
  
 後面接的名稱的範圍解析運算子 \(`::`\) 會構成主要運算式。這類名稱必須是全域範圍的名稱，而不是成員名稱。這個運算式的類型是由名稱的宣告所決定。  如果宣告名稱是左值，它就是左值 \(也就是說，它可以出現在指派運算子運算式左邊\)。  範圍解析運算子允許參考全域名稱，即使該名稱在目前範圍中為隱藏狀態。  如需如何使用範圍解析運算子的範例，請參閱[範圍](../cpp/scope-visual-cpp.md)。  
  
 以括號括住的運算式為主要運算式，其類型和值與未以括號括住之運算式的類型和值相同。  如果未以括號括住的運算式為左值，它就是左值。  
  
 在上述主要運算式語法的內容中，*name* 表示語法中任何針對[名稱](http://msdn.microsoft.com/zh-tw/1c49cc24-08d5-4884-b170-ba8ed42d80db)描述的項目，不過，在名稱前面使用範圍解析運算子時，則不允許只能在類別中出現的名稱類型。這類名稱包括使用者定義的轉換函式名稱和解構函式名稱。  
  
 主要運算式的範例包括：  
  
```  
100 // literal  
'c' // literal  
this // in a member function, a pointer to the class instance  
::func // a global function  
::operator + // a global operator function  
::A::B // a global qualified name  
( i + 1 ) // a parenthesized expression  
```  
  
 以下範例全都會視為各種形式的 *name*，也因此為主要運算式：  
  
```  
MyClass // a identifier  
MyClass::f // a qualified name  
operator = // an operator function name  
operator char* // a conversion operator function name  
~MyClass // a destructor name  
A::B   // a qualified name  
A<int> // a template id  
```  
  
## 請參閱  
 [運算式的類型](../cpp/types-of-expressions.md)