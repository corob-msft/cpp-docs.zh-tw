---
title: /PROFILE (效能工具分析工具)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 26f4ba4efc20f5fee70b2937cdb943689c948888
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519901"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (效能工具分析工具)

產生可與效能工具分析工具搭配使用的輸出檔。

## <a name="syntax"></a>語法

```
/PROFILE
```

## <a name="remarks"></a>備註

/ 設定檔表示下列連結器選項：

- [/OPT: REF](../../build/reference/opt-optimizations.md)

- /OPT: NOICF

- [/INCREMENTAL: NO](../../build/reference/incremental-link-incrementally.md)

- [/FIXED: NO](../../build/reference/fixed-fixed-base-address.md)

/ 設定檔會使連結器在程式映像產生重新配置區段。  重新配置 區段可讓分析工具來轉換程式映像，以取得設定檔資料。

**/ 設定檔**僅只適用於 Enterprise （小組開發） 版本。  如需有關 PREfast 的詳細資訊，請參閱[程式碼分析 C/c + + 概觀](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個連結器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資料，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 展開 [組態屬性] 節點。

1. 依序展開**連結器**節點。

1. 選取 **進階**屬性頁。

1. 修改**設定檔**屬性。

### <a name="to-set-this-linker-option-programmatically"></a>若要以程式設計方式設定這個連結器選項

1. 請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>。

## <a name="see-also"></a>另請參閱

[設定連結器選項](../../build/reference/setting-linker-options.md)<br/>
[連結器選項](../../build/reference/linker-options.md)