---
title: "Visual Studio 中的 Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- visual c++
- visual c
- vc
dev_langs:
- C++
helpviewer_keywords:
- unmanaged code, C++
- development environment, Visual C++
- unmanaged code
- Visual C++
- Visual C++, reference
ms.assetid: e8dcc44c-a3e2-4ffe-887c-fd15b18dc458
caps.latest.revision: 61
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: da3c2e6ce7247d3e8c9a401bc0a133cb8d46a970
ms.openlocfilehash: 81a7d724a4a3b2e5aa7de47461d20cc3385896eb
ms.contentlocale: zh-tw
ms.lasthandoff: 03/15/2017

---
# <a name="visual-c-in-visual-studio"></a>Visual Studio 中的 Visual C++
Visual Studio 2017 程式設計語言和開發工具可協助您開發原生通用 Windows 應用程式、原生傳統型和伺服器應用程式、在 Android 和 iOS 以及 Windows 上執行的跨平台程式庫，以及在 .NET Framework 上執行的 Managed 應用程式。  
  
 **這份文件的對象是哪類讀者？**  
  
 本內容是為撰寫程式的 C++ 開發人員所撰寫。  
  
-   如果您在尋找 C++ 可轉散發套件及執行階段元件以便執行程式，請前往 [Microsoft 下載中心](http://www.microsoft.com/en-us/download/) ，並在搜尋方塊中輸入 **Visual C++** 。  
  
-   如果您在尋找 C++ 程式設計概念的簡介，請前往其中一個提供此內容的網站，或取得一份由 C++ 發明人 Bjarne Stroustup 所著的 [程式設計 - 使用 C++ 的原則和作法 (第二版)](http://stroustrup.com/Programming/) 。 Visual C++ 內容假定您已經對 C++ 有基本的熟悉程度。  
  
-   如果您在尋找 Visual C++ 編譯器，則必須從 [https://www.visualstudio.com/](https://www.visualstudio.com/) 下載付費或免費的 Visual Studio 版本。  

## <a name="general-information-about-visual-c"></a>有關 Visual C++ 的一般資訊  
 [Visual C++ 的新功能](what-s-new-for-visual-cpp-in-visual-studio.md)  
 了解 Visual C++ 的新功能。  

 [Visual Studio 2017 中的 C++ 一致性改善](cpp-conformance-improvements-2017.md) 
 了解 Visual Studio 2017 中的 C++ 一致性改善。 

 [Visual C++ 語言一致性](visual-cpp-language-conformance.md)  
 Visual C++ 依據功能的一致性狀態清單。

 [Visual C++ 變更歷程記錄 2003 - 2015](porting/visual-cpp-change-history-2003-2015.md)  
 了解舊版的重大變更。  
  
 [歡迎回到 C++](cpp/welcome-back-to-cpp-modern-cpp.md)  
 深入了解奠基於 C++11 及 C++14 的新式 C++ 程式設計技術，這項技術讓您能夠撰寫快速、安全的程式碼，並避免許多 C 語言程式設計的常見錯誤。  
  
 [如何回報 Visual C++ 工具組問題](how-to-report-a-problem-with-the-visual-cpp-toolset.md)  
 了解如何針對 Visual C++ 工具組 (編譯器、連結器及其他工具) 建立有效的錯誤報表，以及提交報表的方式。  
  
 [Visual C++ 移植和升級指南](porting/visual-cpp-porting-and-upgrading-guide.md)  
 在 Visual Studio 2017 中移植程式碼到 Visual C++ 及將專案升級至 Visual C++ 的指引，包括將 C++ 程式碼移植到 Windows 10 及通用 Windows 平台。  
  
 [Visual C++ Team Blog](http://blogs.msdn.com/b/vcblog/) (Visual C++ 小組部落格)  
 進一步了解新功能以及 [!INCLUDE[vcprvc](build/includes/vcprvc_md.md)] 開發人員提供的最新資訊。  
  
 [Visual Studio 下載](http://go.microsoft.com/fwlink/?LinkId=235233)  
 下載 Visual C++。  
  
 [Visual Studio 版本中的 Visual C++ 工具和功能](ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)  
 了解不同的 Visual Studio 版本。  
  
 [支援的平台](supported-platforms-visual-cpp.md)  
 了解支援的平台。  
  
 [Visual C++ 範例](visual-cpp-samples.md)  
 有關範例的資訊。  
  
 [Visual Studio Community](http://go.microsoft.com/fwlink/?LinkId=235296)  
 了解如何取得協助、提報 Bug，以及提供有關 Visual Studio 的建議。  
  
## <a name="writing-applications-in-c"></a>使用 C++ 撰寫應用程式  
 [通用 Windows 應用程式](windows/universal-windows-apps-cpp.md)  
 尋找 Windows 開發人員中心網站上的指南和參考內容。 如需開發 Windows 市集應用程式的詳細資訊，請參閱 [使用 Visual Studio 開發 Windows 市集應用程式](http://go.microsoft.com/fwlink/p/?LinkId=248364) 和 [使用 C++ 建立 Windows 市集應用程式的藍圖](http://go.microsoft.com/fwlink/p/?LinkId=244654)。  
  
 [傳統型應用程式 (Visual C++)](windows/desktop-applications-visual-cpp.md)  
 學習如何建立含有訊息迴圈和回呼的桌面應用程式。  
  
 [Visual C++ 中的 DLL](build/dlls-in-visual-cpp.md)  
 了解如何使用 Win32、ATL 和 MFC 建立 Windows 桌面 DLL，並且提供如何編譯和註冊 DLL 的資訊。  
  
 [平行程式設計](parallel/parallel-programming-in-visual-cpp.md)  
 學習如何使用平行模式程式庫 (PPL)、C++ AMP、OpenMP 以及和 Windows 多執行緒相關的其他功能。  
  
 [安全性最佳做法](security/security-best-practices-for-cpp.md)  
 學習如何保護應用程式以防止惡意程式碼並免於未經授權的使用。  
  
 [雲端和 Web 程式設計](cloud/cloud-and-web-programming-in-visual-cpp.md)  
 在 C++ 中，您有數個選項可以連接到 Web 和雲端。  
  
 [資料存取](http://msdn.microsoft.com/Library/a9455752-39c4-4457-b14e-197772d3df0b)  
 使用 ODBC 和其他資料庫存取技術連接到資料庫。  
  
 [文字和字串](text/text-and-strings-in-visual-cpp.md)  
 了解如何使用不同的文字及字串格式化與編碼，進行本機和國際開發。  
  
## <a name="c-development-tools"></a>C++ 開發工具  
 若要了解如何建立專案、使用原始程式碼檔、連結至程式庫、編譯、偵錯、程式碼剖析、部署等等，請參閱 [IDE 和開發工具](ide/ide-and-tools-for-visual-cpp-development.md)。  
  
## <a name="c-language-reference"></a>C++ 語言參考  
 如需 C++ 語言的資訊，請參閱 [C++ 語言參考](cpp/cpp-language-reference.md)。  
  
 如需 C++ 前置處理器的資訊，請參閱 [C/C++ 前置處理器參考](preprocessor/c-cpp-preprocessor-reference.md)。  
  
## <a name="c-libraries-in-visual-studio"></a>Visual Studio 中的 C++ 程式庫  
 下列各節提供 Visual C++ 所包含的不同 C++ 程式庫的相關資訊。  
  
 [C 執行階段程式庫參考](c-runtime-library/c-run-time-library-reference.md)  
 包含已知會造成安全性問題的函式的安全性增強替代項目。  
  
 [C++ 標準程式庫](standard-library/cpp-standard-library-reference.md)  
 C++ 標準程式庫。  
  
 [Active Template Library (ATL)](atl/atl-com-desktop-components.md)  
 對 COM 元件和應用程式的支援。  
  
 [Microsoft Foundation Class (MFC) 程式庫](mfc/mfc-desktop-applications.md)  
 對建立具有傳統或 Office 樣式使用者介面的桌面應用程式的支援。  
  
 [平行模式程式庫 (PPL)](parallel/concrt/parallel-patterns-library-ppl.md)  
 CPU 上執行的非同步和平行演算法。  
  
 [C++ AMP (C++ Accelerated Massive Parallelism)](parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 GPU 上執行的大量平行演算法。  
  
 [Windows 執行階段範本庫 (WRL)](http://msdn.microsoft.com/library/windows/apps/hh438466.aspx)  
 [!INCLUDE[win8_appname_long](build/includes/win8_appname_long_md.md)] 應用程式和元件。  
  
 [以 C++/CLI 進行 .NET 程式設計 (Visual C++)](dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)  
 通用語言執行平台 (CLR) 的程式設計。  
  
 另請參閱 [STL/CLR](dotnet/stl-clr-library-reference.md) 和 [C++ 支援程式庫](dotnet/cpp-support-library.md)的文件。  
  
## <a name="other-c-libraries"></a>其他 C++ 程式庫  
 本節包含未隨附於 Visual Studio 中，但可以下載並搭配 Visual C++ 使用的程式庫連結。  
  
 [Boost](http://www.boost.org/)  
 熱門並廣泛使用的程式庫。  
  
 [C++ REST SDK](http://casablanca.codeplex.com)。  
 透過 HTTP 與 Web 服務通訊的 Microsoft 程式庫。  
  
## <a name="more-resources"></a>更多資源  
 [Visual C++ 資源](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 其他 Visual C++ 資源。  
  
 [標準 C++](http://isocpp.org/)  
 深入了解 C++、取得 Modern C++ 的概觀，以及找到相關書籍、文件、討論和活動的連結  
  
 [了解 Visual C++](http://msdn.microsoft.com/vstudio/hh386302.aspx)  
 開始學習 C++。  
  
## <a name="see-also"></a>另請參閱  
 [C 語言參考](c-language/c-language-reference.md)   
 [C 執行階段程式庫參考](c-runtime-library/c-run-time-library-reference.md)   
 [編譯器內建和組件語言](intrinsics/compiler-intrinsics-and-assembly-language.md)
