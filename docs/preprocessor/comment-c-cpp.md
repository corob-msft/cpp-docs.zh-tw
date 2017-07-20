---
title: "comment (C/C++) | Microsoft Docs"
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
  - "vc-pragma.comment"
  - "comment_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "註釋 [C++]"
  - "comment pragma"
  - "註解 [C++], 編譯的檔案"
  - "Pragma, 註解"
ms.assetid: 20f099ff-6303-49b3-9c03-a94b6aa69b85
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# comment (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

將註解記錄放入目的檔或可執行檔中。  
  
## 語法  
  
```  
  
#pragma comment( comment-type [,"commentstring"] )  
```  
  
## 備註  
 *comment\-type* 是其中一個預先定義的識別項 \(如下所述\)，用於指定註解記錄的類型。  選擇性 `commentstring` 是字串常值，可提供部分註解類型的額外資訊。  由於 `commentstring` 是字串常值，因此它必須遵守字串常值的所有規則，包括逸出字元、內嵌引號 \(**"**\) 和串連等方面。  
  
 **compiler**  
 將編譯器的名稱和版本號碼放入目的檔中。  連結器會忽略這個註解記錄。  如果您為這個記錄類型提供 `commentstring` 參數，則編譯器會產生警告。  
  
 **exestr**  
 在目的檔中放入 `commentstring`。  在連結階段，這個字串會放入可執行檔中。  字串不會在載入可執行檔時一併載入記憶體中，不過，當程式在檔案中尋找可列印字串時就可以找到這些字串。  這個 comment\-record 類型的其中一種用法，是在可執行檔中內嵌版本號碼或類似的資訊。  
  
 `exestr` 已被取代，將在未來版本中移除。連結器不會處理註解記錄。  
  
 **lib**  
 在目的檔中放入程式庫搜尋記錄。  這個註解類型必須搭配 `commentstring` 參數，包含您要連結器搜尋之程式庫的名稱 \(可能還包括路徑\)。  程式庫名稱會遵循目的檔中的預設程式庫搜尋記錄，而連結器會搜尋這個程式庫，就如同您已在命令列上將其命名一樣 \(假設未使用 [\/nodefaultlib](../build/reference/nodefaultlib-ignore-libraries.md) 指定程式庫\)。  您可以在同一個原始程式檔中放入多個程式庫搜尋記錄，每一個記錄都會依照本身在原始程式檔中產生的順序出現在目的檔中。  
  
 如果預設程式庫和加入之程式庫的順序很重要，則使用 [\/Zl](../build/reference/zl-omit-default-library-name.md) 參數進行編譯將可避免將預設程式庫名稱放入物件模組中。  然後就可以使用第二個註解 pragma 將預設程式庫的名稱插入已加入之程式庫的後面。  使用這些 pragma 列出的程式庫將依照它們在原始程式碼中的順序出現在物件模型中。  
  
 **linker**  
 在目的檔中放入[連結器選項](../build/reference/linker-options.md)。  您可以使用這個註解類型指定連結器選項，而不要將其傳遞到命令列或是在開發環境中指定。  例如，您可以指定 \/include 選項強制包含符號：  
  
```  
#pragma comment(linker, "/include:__mySymbol")  
```  
  
 只有下列 \(*comment\-type*\) 連結器選項才可傳遞至連結器識別項：  
  
-   [\/DEFAULTLIB](../build/reference/defaultlib-specify-default-library.md)  
  
-   [\/EXPORT](../build/reference/export-exports-a-function.md)  
  
-   [\/INCLUDE](../build/reference/include-force-symbol-references.md)  
  
-   [\/MANIFESTDEPENDENCY](../build/reference/manifestdependency-specify-manifest-dependencies.md)  
  
-   [\/MERGE](../build/reference/merge-combine-sections.md)  
  
-   [\/SECTION](../build/reference/section-specify-section-attributes.md)  
  
 **User \- 使用者**  
 將一般註解放入目的檔中。  `commentstring` 參數包含註解的文字。  連結器會忽略這個註解記錄。  
  
 下列 pragma 會使連結器在連結時搜尋 EMAPI.LIB 程式庫。  連結器會先搜尋目前的工作目錄，然後再搜尋 LIB 環境變數中所指定的路徑。  
  
```  
#pragma comment( lib, "emapi" )  
```  
  
 下列 pragma 會讓編譯器將編譯器的名稱和版本號碼放入目的檔中：  
  
```  
#pragma comment( compiler )  
```  
  
> [!NOTE]
>  對於採用 `commentstring` 參數的註解，可以在您會使用字串常值的任何地方使用巨集 \(假設巨集會展開為字串常值\)。  您也可以串連任何的組合，其中包括字串常值以及可展開為字串常值的巨集。  例如，以下是可接受的陳述式：  
  
```  
#pragma comment( user, "Compiled on " __DATE__ " at " __TIME__ )   
```  
  
## 請參閱  
 [Pragma 指示詞和 \_\_Pragma 關鍵字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)