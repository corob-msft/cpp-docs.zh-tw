---
title: "C 宣告和定義 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
ms.assetid: 575f0c9b-5554-4346-be64-b2129ca9227f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C 宣告和定義
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

「宣告」會在特定變數、函式或類型及其屬性之間建立關聯。  [宣告概觀](../c-language/overview-of-declarations.md)中提供了 `declaration` 非終端項的 ANSI 語法。  宣告也會指定識別項可以存取的位置和時間 \(識別項的「連結」\)。  如需連結的詳細資訊，請參閱[存留期、範圍、可視性和連結](../c-language/lifetime-scope-visibility-and-linkage.md)。  
  
 變數的「定義」會建立與宣告相同的關聯，但也會為變數配置儲存區。  
  
 例如，`main`、`find` 和 `count` 函式，以及 `var` 和 `val` 變數是在某個原始程式檔中定義，順序如下：  
  
```  
int main() {}  
  
int var = 0;  
double val[MAXVAL];  
char find( fileptr ) {}  
int count( double f ) {}  
```  
  
 變數 `var` 和 `val` 可用於 `find` 和 `count` 函式，不需要進一步宣告。  但是，這些名稱在 `main` 中是不可見的 \(無法存取\)。  
  
## 請參閱  
 [原始程式檔和來源程式](../c-language/source-files-and-source-programs.md)