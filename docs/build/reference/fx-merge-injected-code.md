---
title: "/Fx (合併插入的程式碼) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.ExpandAttributedSource"
  - "/Fx"
  - "VC.Project.VCCLCompilerTool.ExpandAttributedSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fx 編譯器選項 [C++]"
  - "-Fx 編譯器選項 [C++]"
  - "插入程式碼"
  - "合併插入程式碼"
  - "/Fx 編譯器選項 [C++]"
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Fx (合併插入的程式碼)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

產生每個原始程式檔的複本，並將插入的程式碼合併到原始程式檔中。  
  
## 語法  
  
```  
/Fx  
```  
  
## 備註  
 為了區分已合併的原始程式檔與原先的原始程式檔，**\/Fx** 會在檔案名稱與副檔名之間加入 .mrg 副檔名。 例如，含有使用屬性之程式碼並以 **\/Fx** 建置的檔案 MyCode.cpp，會建立含有下列程式碼的檔案 MyCode.mrg.cpp：  
  
```  
//+++ Start Injected Code [no_injected_text(true)];      // Suppress injected text, it has // already been injected #pragma warning(disable: 4543) // Suppress warnings about skipping // injected text #pragma warning(disable: 4199) // Suppress warnings from attribute // providers //--- End Injected Code  
```  
  
 在 .mrg 檔中，由於屬性所插入的程式碼會以下列方式分隔：  
  
```  
//+++ Start Injected Code ... //--- End Injected Code  
```  
  
 [no\_injected\_text](../../windows/no-injected-text.md) 屬性會內嵌於 .mrg 檔中，因此可直接編譯 .mrg 檔，而不需要重新插入文字。  
  
 請注意，.mrg 原始程式檔是為了表示編譯器所插入的原始程式碼。 .mrg 檔的編譯和執行可能不會與原先的原始程式檔完全一樣。  
  
 .mrg 檔中不會展開巨集。  
  
 如果您的程式包含使用插入程式碼的標頭檔，**\/Fx** 會為該標頭產生 .mrg.h 檔。**\/Fx** 不會合併未使用插入程式碼的 Include 檔。  
  
### 在 Visual Studio 開發環境中設定這個編譯器選項  
  
1.  開啟專案的 \[屬性頁\] 對話方塊。 如需詳細資訊，請參閱[如何：開啟專案屬性頁](../../misc/how-to-open-project-property-pages.md)。  
  
2.  按一下 \[C\/C\+\+\] 資料夾。  
  
3.  按一下 \[輸出檔\] 屬性頁。  
  
4.  修改 \[展開屬性化來源\] 屬性。  
  
### 若要以程式方式設定這個編譯器選項  
  
-   請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>。  
  
## 請參閱  
 [輸出檔 \(\/F\) 選項](../../build/reference/output-file-f-options.md)   
 [編譯器選項](../../build/reference/compiler-options.md)   
 [設定編譯器選項](../../build/reference/setting-compiler-options.md)