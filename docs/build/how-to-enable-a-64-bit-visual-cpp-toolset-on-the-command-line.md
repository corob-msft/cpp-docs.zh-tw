---
title: 如何：在命令列啟用 64 位元 Visual C++ 工具組
ms.date: 03/29/2018
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
ms.openlocfilehash: 5c5fe144fe81fcc0fb1194c57dec7fa7556101f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572363"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>如何： 啟用 64 位元、 x64 裝載在命令列上的 Visual c + + 工具組

Visual c + + 包含編譯器、 連結器及其他工具，可用來建立您可以在 32 位元、 64 位元或 ARM 為基礎的 Windows 作業系統執行的應用程式的平台特定版本。 其他選擇性的 Visual Studio 工作負載可讓您使用 c + + 工具來鎖定，請在其他平台，例如 iOS、 Android 及 Linux。 預設組建架構會使用 32 位元、 x86 裝載的工具來建置 32 位元、 x86 原生 Windows 程式碼。 不過，您可能必須在 64 位元電腦。 您可以善用處理器和記憶體的可用空間 64 位元程式碼使用 64 位元、 x64 裝載工具組，當您建置適用於 x86、 x64 或 ARM 處理器的程式碼。

> [!NOTE]
> 隨附於 Visual c + + 中的每個版本的特定工具的相關資訊，請參閱[Visual c + + 工具和 Visual Studio 版本中的功能](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md)。
>
> 如需有關如何使用 Visual Studio IDE 建立 64 位元應用程式的資訊，請參閱 <<c0> [ 如何： 將 Visual c + + 專案設定為目標的 64 位元，x64 平台](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)。

當您在 Visual Studio 安裝程式中安裝 c + + 工作負載時，一律都會安裝 32 位元、 x86 裝載、 原生和跨編譯器來建置 x86 和 x64 的程式碼的工具。 如果您包含通用 Windows 平台的工作負載時，它也會安裝 x86 裝載的跨平台編譯器工具來建置 ARM 程式碼。 如果您在 64 位元，x64 上安裝這些工作負載的處理器，您也取得 64 位元原生和跨編譯器工具來建置 x86、 x64、 及 ARM 程式碼。 32 位元和 64 位元工具產生相同的程式碼，但 64 位元工具支援更多記憶體的先行編譯標頭符號和整個程式最佳化 ([/GL](../build/reference/gl-whole-program-optimization.md)並[/LTCG](../build/reference/ltcg-link-time-code-generation.md)) 選項。 如果您會遇到記憶體限制，當您使用 32 位元工具，請嘗試 64 位元工具。

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>使用 64 位元裝載的開發人員命令提示字元捷徑

在 64 位元 Windows 作業系統上安裝 Visual Studio，都可以使用其他開發人員命令提示字元 捷徑的 64 位元，x64 架構的原生和跨平台編譯器。 若要存取在 Windows 10 上的這些命令提示字元**開始**] 功能表中，開啟您的 Visual Studio 版本的資料夾，例如**Visual Studio 2017**，然後選擇 [x64 native 或跨工具開發人員命令提示字元。 若要存取這些命令提示字元，在 Windows 8 中，在**開始**畫面上，開啟**所有應用程式**。 在已安裝版本的 Visual Studio 標題下，開啟**Visual Studio**資料夾 (在舊版的 Visual Studio 中，它可能會命名**Visual Studio Tools**)。 在舊版 Windows 中，選擇**開始**，展開**所有程式**，用於您版本的資料夾**Visual Studio** (和較舊版本的 Visual Studio 中上, **Visual Studio Tools**)。 如需詳細資訊，請參閱[開發人員命令提示字元捷徑](../build/building-on-the-command-line.md#developer-command-prompt-shortcuts)。

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>使用 Vcvarsall.bat 設定 64 位元裝載的組建架構

任何原生，或是跨編譯器工具組建組態可以使用命令列，執行 vcvarsall.bat 命令檔。 此命令檔會設定的路徑和環境變數，讓特定建置在現有的 [命令提示字元] 視窗中的架構。 特定的指示，請參閱[開發人員命令檔案和位置](../build/building-on-the-command-line.md#developer-command-files-and-locations)。

## <a name="see-also"></a>另請參閱

[針對 64 位元 x64 目標設定 Visual C++](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
