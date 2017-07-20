---
title: "歡迎回到 C++ (現代 C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1cb1b849-ed9c-4721-a972-fd8f3dab42e2
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 歡迎回到 C++ (現代 C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 是世界上最廣泛使用的程式語言之一。  編寫完善的 C\+\+ 程式不但執行快速，而且有效率。  這種語言較其他語言更具彈性，因為您可以用它來建立各種應用程式，從好玩刺激的遊戲到高效能科學軟體、裝置驅動程式、內嵌程式和 Windows 用戶端應用程式，一應俱全。  20 多年來，C\+\+ 已經用來解決這類和許多其他的問題。  您可能不知道的是，有越來越多的 C\+\+ 程式設計人員已經捲藏過時的 C\-Style 程式設計舊衣，換上了現代 C\+\+ 的新裝。  
  
 C\+\+ 的其中一個原始需求是與 C 語言的回溯相容性。  從那時起，C\+\+ 就幾經更迭，逐漸發展成形；先是具有類別的 C，繼而有原始的 C\+\+ 語言規格，然後加入許多後續的增強功能。  由於這樣的傳承，C\+\+ 通常稱為多典範程式語言。  在 C\+\+ 中，您可以單純地進行程序式 C\-Style 程式設計，包括可能獲致絕佳效能的原始指標、陣列、null 結尾字元字串、自訂資料結構及其他功能，但也可能孳生 Bug 和複雜性。  由於 C\-Style 程式設計充滿這類的危險，C\+\+ 其中一個建置目標就是讓程式為類型安全，而且更容易撰寫、擴充和維護。  C\+\+ 在初期接受物件導向程式設計之類的程式設計典範。  多年來，已有許多功能跟隨多方測試的結構與演算法標準程式庫一起加入這個語言的陣容。  也就是這些新增功能造就了現代 C\+\+ 樣式。  
  
 現代 C\+\+ 著重於：  
  
-   堆疊式範圍，而不是堆積或靜態全域範圍。  
  
-   自動類型推斷，而不是明確類型名稱。  
  
-   智慧型指標，而不是原始指標。  
  
-   `std::string` 和 `std::wstring` 類型 \(請參閱 [\<string\>](../standard-library/string.md)\)，而不是未經處理的 `char[]` 陣列。  
  
-   [標準範本庫](../standard-library/cpp-standard-library-header-files.md) \(STL\) 容器 \(例如 `vector`、`list` 和 `map`\)，而不是原始陣列或自訂容器。  請參閱[\<vector\>](../standard-library/vector.md)、[\<list\>](../standard-library/list.md)和[\< 對應 \>](../standard-library/map.md)。  
  
-   [STL 演算法](../standard-library/algorithm.md)，而不是手動撰寫的演算法程式碼。  
  
-   例外狀況，用來報告和處理錯誤狀況。  
  
-   使用 STL `std::atomic<>` \(請參閱 [\<atomic\>](../standard-library/atomic.md)\) 的無鎖定執行緒間通訊，而不是其他執行緒間的通訊機制。  
  
-   內嵌 [Lambda 函式](../cpp/lambda-expressions-in-cpp.md)，而不是個別實作的小型函式。  
  
-   範圍架構的 for 迴圈，用來撰寫更強固的、以 `for ( for-range-declaration : expression )` 的形式，搭配使用陣列、STL 容器和 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]集合的迴圈。  這是核心語言支援的一部分。  如需詳細資訊，請參閱[以範圍為基礎的 for 陳述式 \(C\+\+\)](../cpp/range-based-for-statement-cpp.md)。  
  
 C\+\+ 語言本身也有所演變。  比較下列程式碼片段。  這是顯示 C\+\+ 過去一般狀況的程式碼片段：  
  
```cpp  
  
// circle and shape are user-defined types  
circle* p = new circle( 42 );   
vector<shape*> v = load_shapes();  
  
for( vector<circle*>::iterator i = v.begin(); i != v.end(); ++i ) {  
    if( *i && **i == *p )  
        cout << **i << “ is a match\n”;  
}  
  
for( vector<circle*>::iterator i = v.begin();  
        i != v.end(); ++i ) {  
    delete *i; // not exception safe  
}  
  
delete p;  
  
```  
  
 在現代 C\+\+ 中達成相同狀況的做法如下：  
  
```cpp  
  
#include <memory>  
#include <vector>  
// ...  
// circle and shape are user-defined types  
auto p = make_shared<circle>( 42 );  
vector<shared_ptr<shape>> v = load_shapes();  
  
for_each( begin(v), end(v), [&](const shared_ptr<shape>& s) {  
    if( s && *s == *p )  
        cout << *s << " is a match\n";  
} );  
  
```  
  
 在現代 C\+\+ 中，因為可以改用智慧型指標，就不需要使用 new\/delete 或明確例外狀況處理。  當您使用 `auto` 類型推算和 [Lambda 函式](../cpp/lambda-expressions-in-cpp.md)時，可以更快速撰寫、更強化且更容易了解程式碼。  `for_each` 會比 `for` 迴圈更清楚、更輕鬆使用，而且比較不容易發生未知的錯誤。  您可以使用未定案程式碼搭配最少的程式行來撰寫應用程式。  您可以使該程式碼成為記憶體安全和例外狀況安全，而且沒有要處理的配置\/解除配置或錯誤碼。  
  
 現代 C\+\+ 結合了兩種多型：編譯時期 \(透過樣板\) 和執行階段 \(透過繼承和虛擬化\)。  您可以混合使用這兩種多型來產生良好效果。  STL 樣板 `shared_ptr` 使用內部虛擬方法，完成其顯然毫不費力的類型清除。  但是當範本是較佳選擇時，請勿對多型過度使用虛擬。  樣板有可觀的強大功能。  
  
 如果您是從其他語言改換過來使用 C\+\+，特別是從類型多半為參考類型、少有實值類型的 Managed 語言過來，請記得 C\+\+ 類別預設是實值類型。  但是您可以將這些類別指定為參考類型，啟用支援物件導向程式設計的多型行為。  有用的觀點：實值類型與記憶體及配置控制較有關聯，參考類型則多偏向支援多型的基底類別及虛擬函式。  根據預設，實值類型是可複製的，每個類型都具有複製建構函式和複製指派運算子。  當您指定參考類型時，請將類別設定為不可複製 \(停用複製建構函式和複製指派運算子\)，並使用支援多型的虛擬解構函式。  實值類型也是與內容有關，當您複製這些內容時，會取得兩個可分別修改的獨立值。  但是參考類型則與識別有關 \(屬於哪種物件\)，因此有時稱為多型類型。  
  
 C\+\+ 正在復活，因為功能強大再度成為王道。  當程式設計人員產能很重要時，像 Java 和 C\# 這樣的語言很適用，但是當功能與效能變得至關重要時，這些語言就顯得有所局限。  就高效率和功能而論，尤其是在硬體資源有限的裝置上，所有語言都比不上現代 C\+\+。  
  
 不僅語言現代，連開發工具也是。  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 穩固且有效率地打造開發週期的所有環節。  這包含 Application Lifecycle Management \(ALM\) 工具、IDE 增強功能 \(例如 IntelliSense\)、工具易用的機制 \(例如 XAML\) 以及建置、偵錯等許多其他工具。  
  
 本文件中的這篇文章針對撰寫現代 C\+\+ 程式所需的最重要功能及技術，提供了高階方針和最佳作法。  
  
-   [C\+\+11\/14\/17 功能的支援](../cpp/support-for-cpp11-14-17-features-modern-cpp.md)  
  
-   [C\+\+ 類型系統](../cpp/cpp-type-system-modern-cpp.md)  
  
-   [統一初始設定和委派建構函式](../cpp/uniform-initialization-and-delegating-constructors.md)  
  
-   [物件存留期和資源管理](../cpp/object-lifetime-and-resource-management-modern-cpp.md)  
  
-   [物件擁有資源 \(RAII\)](../cpp/objects-own-resources-raii.md)  
  
-   [智慧型指標](../cpp/smart-pointers-modern-cpp.md)  
  
-   [編譯時期封裝的 Pimpl](../cpp/pimpl-for-compile-time-encapsulation-modern-cpp.md)  
  
-   [容器](../cpp/containers-modern-cpp.md)  
  
-   [演算法](../cpp/algorithms-modern-cpp.md)  
  
-   [字串和 I\/O 格式化](../cpp/string-and-i-o-formatting-modern-cpp.md)  
  
-   [錯誤和例外狀況處理](../cpp/errors-and-exception-handling-modern-cpp.md)  
  
-   [ABI 界限上的可攜性](../cpp/portability-at-abi-boundaries-modern-cpp.md)  
  
 如需詳細資訊，請參閱 StackOverflow 文章 [C\+\+11 中已取代的 C\+\+ 慣用語](http://go.microsoft.com/fwlink/?LinkId=402836) \(英文\)  
  
## 請參閱  
 [C\+\+ 語言參考](../cpp/cpp-language-reference.md)   
 [Lambda 運算式](../cpp/lambda-expressions-in-cpp.md)   
 [C\+\+ Standard Library](../standard-library/cpp-standard-library-reference.md)