---
title: "連結器工具錯誤 LNK2001 |Microsoft 文件"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2001
dev_langs: C++
helpviewer_keywords: LNK2001
ms.assetid: dc1cf267-c984-486c-abd2-fd07c799f7ef
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 51f78f436d0e19779d0ebca499a559a60d12bcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2001"></a>連結器工具錯誤 LNK2001
未解析外部符號"*符號*"  
  
已編譯的程式碼會參考或呼叫*符號*，但該符號未定義的任何程式庫或物件給連結器指定的檔案。  
  
這則錯誤訊息後面接著嚴重錯誤[LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)。 您必須修正若要修正錯誤 LNK1120 所有 LNK2001 和 LNK2019 錯誤。  
  
## <a name="possible-causes"></a>可能的原因  
  
有許多方法，以取得此錯誤，但全部都涉及的函式或變數，連結器無法參考*解決*，或找不到的定義。 編譯器能夠識別時的符號不*宣告*，但不是在未*定義*，因為定義可能是不同原始程式檔或程式庫中。 如果符號為參考，但永遠不會定義，連結器會產生錯誤。  
  
### <a name="coding-issues"></a>程式碼的問題  
  
這個錯誤可能因不相符的情況下，在您的原始碼或模組定義 (.def) 檔。 例如，如果名稱變數`var1`一個 c + + 來源檔案，並嘗試存取它做為`VAR1`位於另一個，就會產生這個錯誤。 若要修正此問題，使用一致的方式使用的拼字和大小寫名稱。  
  
此錯誤可能造成的專案中，使用[函式內嵌](../../error-messages/tool-errors/function-inlining-problems.md)如果您在原始程式檔中，而不是標頭檔中定義的函式。 無法看到內嵌函式外定義它們的原始程式檔。 若要修正此問題，請在宣告它們的標頭中定義內嵌函式。  
  
如果您從 c + + 程式呼叫 C 函式而不使用，可能會造成這個錯誤`extern "C"`C 函式宣告。 編譯器會使用不同的內部符號命名慣例的 C 和 c + + 程式碼，而且連結器會尋找解析符號時的內部的符號名稱。 若要修正此問題，請使用`extern "C"`包裝函式，用於您的 c + + 程式碼，而導致編譯器要用於這些符號 C 內部命名慣例的 C 函式的所有宣告。 編譯器選項[/Tp](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)和[/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)會造成編譯器將檔案編譯為 c + + 或 C，分別不論檔名的副檔名。 這些選項可能會導致不同於您所預期的內部函式名稱。  
  
這個錯誤可能被因嘗試參考函式或不具有外部連結的資料。 C + + 內嵌函式和`const`資料具有內部連結，除非明確指定為`extern`。 若要修正此問題，請使用明確`extern`上符號的宣告參考外部定義的原始程式檔。  
  
這個錯誤可能因[遺漏函式主體或變數](../../error-messages/tool-errors/missing-function-body-or-variable.md)定義。 當您宣告，但未定義、 變數、 函數或類別在程式碼中，此錯誤是常見的。 編譯器只需要函式原型或`extern`變數的宣告來產生物件檔案不含錯誤，但連結器無法解析呼叫函式或變數的參考，因為沒有函式程式碼或變數空間保留。 若要修正此問題，請確定每個參考的函式和變數是完全在中定義之原始程式檔或程式庫包含在您的連結。  
  
這個錯誤可能被因使用傳回和參數類型或不符合函式定義中的呼叫慣例的函式呼叫。 在 c + + 物件檔，[名稱裝飾](../../error-messages/tool-errors/name-decoration.md)納入最終的裝飾函式名稱，用做要比對時的符號呼叫的呼叫慣例、 類別或命名空間範圍和函式的傳回和參數類型會解析函式的其他物件檔案。 若要修正此問題，請確定宣告、 定義和呼叫所有函式使用相同範圍、 類型和呼叫慣例。  
  
此錯誤可能造成在 c + + 程式碼中，當您在類別定義中包含函式原型，但無法[包含實作](../../error-messages/tool-errors/missing-function-body-or-variable.md)函式，然後呼叫它。 若要修正此問題，請務必提供所有呼叫的定義宣告類別的成員。  
  
這個錯誤可能被因嘗試從抽象的基底類別呼叫純虛擬函式。 純虛擬函式會有任何基底類別實作。 若要修正此問題，請確定所有呼叫虛擬函式實作。  
  
這個錯誤可能因嘗試使用函式中宣告的變數 ([區域變數](../../error-messages/tool-errors/automatic-function-scope-variables.md)) 在該函式範圍之外。 若要修正此問題，移除不在範圍內，該變數的參考，或將變數移至較高的範圍。  
  
當您建置發行版本的 ATL 專案，產生一則訊息 CRT 啟始程式碼所需，就會發生此錯誤。 若要修正此問題，請執行下列其中一項  
  
-   移除`_ATL_MIN_CRT`清單中的前置處理器定義允許要包含的 CRT 啟始程式碼。 請參閱[一般屬性頁 （專案）](../../ide/general-property-page-project.md)如需詳細資訊。  
  
-   可能的話，請移除需要 CRT 啟始程式碼的 CRT 函式呼叫。 相反地，Win32 用法。 例如，使用`lstrcmp`而不是`strcmp`。 已知的函式需要 CRT 啟始程式碼是一些字串和浮點函式。  
  
### <a name="compilation-and-link-issues"></a>編譯和連結的問題  
  
專案遺漏程式庫的參考時，會發生此錯誤 (。LIB) 或物件 (。OBJ) 檔案。 若要修正此問題，請將必要的程式庫或物件檔案的參考加入至您的專案。 如需詳細資訊，請參閱[.lib 檔做為連結器輸入](../../build/reference/dot-lib-files-as-linker-input.md)。  
  
如果您使用，可能會發生這個錯誤[/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)或[/Zl](../../build/reference/zl-omit-default-library-name.md)選項。 當您指定這些選項時，包含必要的程式碼的程式庫不會連結到專案除非您明確地包含它們。 若要修正此問題，明確地包含所有您在連結命令列使用的程式庫。 如果您使用這些選項時，您會看到許多遺漏 CRT 或標準程式庫函式名稱，明確包含 CRT 和標準程式庫 Dll 或程式庫檔案的連結。  

如果您將編譯使用**/clr**選項，可以有遺漏參考.cctor。 若要修正這個問題，請參閱[初始化的混合的組件](../../dotnet/initialization-of-mixed-assemblies.md)如需詳細資訊。  
  
如果您連結到發行模式程式庫建置應用程式的偵錯版本時，會發生此錯誤。 同樣地，如果您使用選項**/MTd**或**/MDd**或定義`_DEBUG`然後連結到發行的程式庫，您應該預期許多可能無法解析外部符號，在其他問題。 連結偵錯程式庫的版本模式建置時，也會造成類似的問題。 若要修正此問題，請確定您在偵錯組建中，使用偵錯程式庫和零售程式庫，在您的零售組建。  
  
如果您的程式碼的符號是指從一個版本的程式庫，但是您提供給連結器程式庫的不同版本，就會發生此錯誤。 一般而言，您不能混用目的檔或程式庫，系統會針對不同版本的編譯器建立。 發行新版本中的程式庫可能包含找不到包含在舊版中，與相反的文件庫中的符號。 若要修正此問題，請建置所有目的檔和具有相同版本的編譯器程式庫之前連結在一起。  
  
-  工具 &#124;選項 &#124;專案 &#124;VC + + 目錄 對話方塊中的，在程式庫檔案選取項目，可讓您變更文件庫搜尋順序。 在專案屬性頁對話方塊中的連結器資料夾可能也包含可能是過期的路徑。  
  
-  新的 SDK 會安裝 （或許是為了不同的位置），並搜尋順序不會更新以指向新位置時，可能會出現此問題。 一般來說，您應該將路徑放至新的 SDK 包括和 lib 目錄前面的預設 Visual c + + 的位置。 此外，含有內嵌的路徑的專案可能仍然指向舊的路徑有效，但過期會安裝到不同位置的新版本所加入的新功能。  
  
-   如果您在命令列建置，並已建立您自己的環境變數，請確認工具、 程式庫和標頭檔的路徑，請移至一致性版本。 如需詳細資訊，請參閱[設定命令列建置的路徑和環境變數](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)
  
目前沒有任何標準[c + + 命名](../../error-messages/tool-errors/name-decoration.md)編譯器廠商，或甚至是不同的編譯器版本之間。 因此，連結以其他編譯器編譯的目的檔不可能會產生相同的命名配置，因此會導致錯誤 LNK2001。  
  
[混合的內嵌和非內嵌編譯選項](../../error-messages/tool-errors/function-inlining-problems.md)在不同模組會造成 LNK2001。 C + + 程式庫會透過函式內嵌為開啟 (**/Ob1**或**/Ob2**)，但對應的標頭檔描述該函式已關閉內嵌 (沒有`inline`關鍵字)，這個錯誤就會發生。 若要修正此問題，定義的函式`inline`您在其他原始程式檔中包含的標頭檔中。  
  
如果您使用`#pragma inline_depth`編譯器指示詞，請確定您有[值為 2 或更大的集](../../error-messages/tool-errors/function-inlining-problems.md)，並確定您也使用[/Ob1](../../build/reference/ob-inline-function-expansion.md)或[/Ob2](../../build/reference/ob-inline-function-expansion.md)編譯器選項。  
  
如果您省略此連結，會發生此錯誤選項 /NOENTRY，當您建立僅含資源的 DLL。 若要修正此問題，請將 /NOENTRY 選項加入連結命令。  
  
如果您使用不正確的 /SUBSYSTEM 或 /ENTRY 設定您的專案中，會發生此錯誤。 例如，如果您撰寫主控台應用程式，並指定 /subsystem: windows 時，無法解析的外部錯誤會產生`WinMain`。 若要修正此問題，請確定您比對專案類型的選項。 如需有關這些選項和進入點的詳細資訊，請參閱[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)和[/ENTRY](../../build/reference/entry-entry-point-symbol.md)連結器選項。  
  
### <a name="exported-symbol-issues"></a>匯出的符號問題  
  
找不到匯出.def 檔案中所列時，就會發生此錯誤。 這可能是因為它不存在、 拼法不正確，或使用 c + + 裝飾名稱。 .Def 檔不會將裝飾的名稱。 若要修正此問題，請移除不必要的匯出，並使用`extern "C"`已匯出符號的宣告。  
  
## <a name="what-is-an-unresolved-external-symbol"></a>無法解析的外部符號是什麼？  
  
A*符號*函式或由已編譯的目的檔或程式庫內部使用的全域變數的名稱。 符號是*定義*目的檔的全域變數，或函式儲存體的配置位置放置函式主體的已編譯程式碼中。 *外部符號*是一種符號的*參考*，也就是使用或呼叫在一個物件檔案中，但在不同的文件庫或物件檔案中定義。 *匯出符號*是可公開使用的目的檔或程式庫中定義的其中一個。 連結器必須*解決*，或找不到相符的每個連結到應用程式或 DLL 時，物件檔案所參考的外部符號定義。 無法解析外部符號的任何連結的檔案中尋找相符的匯出的符號時，連結器會產生錯誤。    
  
## <a name="use-the-decorated-name-to-find-the-error"></a>使用裝飾的名稱，找出錯誤
  
C + + 編譯器和連結器使用[名稱裝飾](../../error-messages/tool-errors/name-decoration.md)，亦稱為*名稱改變*，用來編碼之變數的類型或傳回型別、 參數類型、 範圍和呼叫的額外資訊符號名稱的函式的慣例。 此裝飾的名稱是連結器搜尋來解析外部符號的符號名稱。  
  
額外的資訊會成為符號名稱的一部分，因為連結錯誤可能會造成如果函式或變數的宣告不完全符合的函式或變數的定義。 即使在呼叫程式碼和定義的程式碼中，使用相同的標頭檔如果編譯原始程式檔時，會使用不同的編譯器旗標，也可能會發生。 例如，收到此錯誤，如果您的程式碼編譯為使用`__vectorcall`呼叫慣例，但是您連結到需要呼叫它使用預設的用戶端程式庫`__cdecl`或`__fastcall`呼叫慣例。 在此情況下，符號不相符因為不同的呼叫慣例   
  
為了協助您找出這種錯誤的原因，連結器錯誤訊息顯示這兩個 「 易記名稱，"原始程式碼和未解析外部符號的裝飾的名稱 （括號中） 中使用的名稱。 您不需要知道如何轉譯能夠比較它與其他裝飾名稱的裝飾的名稱。 您可以使用隨附於編譯器，來比較預期的符號名稱與實際的符號名稱的命令列工具：  

-   [/Exports](../../build/reference/dash-exports.md)和[/ 符號](../../build/reference/symbols.md)選項 DUMPBIN 命令列工具可協助您探索哪些符號定義在.dll 和物件或程式庫檔案。 您可以使用此驗證匯出裝飾名稱相符連結器搜尋。  
  
在某些情況下，連結器只會報告符號的裝飾的名稱。 UNDNAME 命令列工具可用來取得裝飾名稱的未裝飾的形式。  
  
## <a name="additional-resources"></a>其他資源  
  
如需 LNK2001 可能原因和解決方案的詳細資訊，請參閱 Stack Overflow 的問題[什麼是未定義參考/未解析外部符號錯誤及如何修正問題？](http://stackoverflow.com/q/12573816/2002113)。  
