---
title: 在 Visual Studio 中建置 C++ 專案
ms.date: 11/04/2016
helpviewer_keywords:
- Visual C++ projects, building
- projects [C++], building
- builds [C++], about building in Visual Studio
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
ms.openlocfilehash: 83f79e922a66622611f3f6e493ca8d498435033f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569666"
---
# <a name="building-c-projects-in-visual-studio"></a>在 Visual Studio 中建置 C++ 專案

在 Visual Studio 整合式開發環境 (IDE) 中，有數種方法可以建置整個方案或僅在其中建置一個專案。 您還可以修改建置設定，並指定自訂建置步驟，以讓您的開發處理程序更加有效。

若要建置在 Visual Studio 中開啟且在 [方案總管] 中選取的方案，您可以：

- 在功能表列上，選擇 [建置] 、[建置方案] 。

- 或者，在 [方案總管] 中，開啟方案的捷徑功能表，然後選擇 [建置方案]。

- 或者，按 F7  (這是 C/C++ 開發設定的預設鍵盤捷徑)。

- 或者，在[命令視窗](/visualstudio/ide/reference/command-window) (在功能表列上，選擇 [檢視]、[其他視窗]、[命令視窗]) 中，輸入 `Build.BuildSolution`。

- 或者，在[快速啟動](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box)方塊中，輸入 `build build solution`。

若要建置在 [方案總管] 中選取的專案，您可以：

- 在功能表列上，選擇 [建置]、[建置 \<專案名稱>]。

- 或者，在 [方案總管] 中，開啟專案的捷徑功能表，然後選擇 [建置]。

- 或者，在 [命令視窗] (在功能表列上，選擇 [檢視]、[其他視窗]、[命令視窗]) 中，輸入 `Build.BuildOnlyProject`。

- 或者，在 [快速啟動] 方塊中，輸入 `build project only build only <project name>`。

當您在 Visual Studio 中建置 Visual C++ 應用程式時，您可以在專案的 [屬性頁] 對話方塊中，修改許多建置設定。 如需如何設定專案屬性的資訊，請參閱[使用專案屬性](../ide/working-with-project-properties.md)。

如需如何使用 IDE 來建立、建置及偵錯 C++ 專案的範例，請參閱[逐步解說：使用 C++ 探索 Visual Studio IDE](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)。 如需如何使用 IDE 建置 C++/CLR 專案，請參閱[逐步解說：編譯針對 Visual Studio 中 CLR 的 C++ 程式](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)。 如需如何使用 IDE 來建立 Windows 執行階段應用程式的範例，請參閱[使用 C++ 建立您的第一個 Windows 執行階段應用程式](https://msdn.microsoft.com/library/windows/apps/hh974580.aspx)。

若要閱讀如何建置、修改建置設定及指定自訂建置步驟的更多資訊，請參閱下列文章。

## <a name="in-this-section"></a>本節內容

[了解自訂建置步驟和建置事件](../ide/understanding-custom-build-steps-and-build-events.md)<br>
描述如何在整合式開發環境中自訂建置處理程序。

[建置命令和屬性的一般巨集](../ide/common-macros-for-build-commands-and-properties.md)<br>
列出您可以在接受字串的位置使用的巨集。

[建置外部專案](../ide/building-external-projects.md)<br>
討論使用整合式開發環境外部功能的建置專案。

[專案檔](../ide/project-files.md)<br>
呈現 .vcxproj 檔案的 XML 結構。

## <a name="related-sections"></a>相關章節

[選項對話方塊、專案、VC++ 目錄](vcpp-directories-property-page.md)<br>
(僅限 MSBuild 專案) 討論在建置期間，如何修改可執行檔、Include檔、程式庫檔及原始程式碼檔案的搜尋路徑。

[編譯和建置](/visualstudio/ide/compiling-and-building-in-visual-studio)<br>
提供 Visual Studio 中建置的相關資訊。

[建置 C/C++ 程式](../build/building-c-cpp-programs.md)<br>
提供描述如何從命令列或 Visual Studio 整合式開發環境建置程式等主題的連結。

[C/C++ 建置參考](../build/reference/c-cpp-building-reference.md)<br>
提供以 C++ 建置程式之概觀、編譯器及連結器選項，以及其他建置工具的連結。

[從舊版的 Visual C++ 升級專案](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)<br>
提供涵蓋將 C++ 專案升級至較新版本的編譯器工具組等問題的主題連結。

[Visual C++ 移植和升級指南](../porting/visual-cpp-porting-and-upgrading-guide.md)詳細說明如何升級使用舊版 Visual Studio 所建立的 C++ 應用程式，以及如何移轉使用 Visual Studio 以外的工具建立的應用程式。

## <a name="see-also"></a>請參閱

[通用 Windows 應用程式 (C++)](../windows/universal-windows-apps-cpp.md)