---
title: /Od (停用 (偵錯))
ms.date: 11/04/2016
f1_keywords:
- /od
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
ms.openlocfilehash: b7cbf8de06e698e67e370eb399da5bb00b262895
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595789"
---
# <a name="od-disable-debug"></a>/Od (停用 (偵錯))

關閉程式中的所有最佳化並加速進行編譯。

## <a name="syntax"></a>語法

```
/Od
```

## <a name="remarks"></a>備註

此選項是預設值。 因為 **/Od**隱藏程式碼移動，它可簡化偵錯程序。 如需編譯器選項進行偵錯的詳細資訊，請參閱[/z7，/Zi，/ZI （偵錯資訊格式）](../../build/reference/z7-zi-zi-debug-information-format.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項

1. 開啟專案的 [屬性頁]  對話方塊。 如需詳細資料，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 按一下 [C/C++]  資料夾。

1. 按一下 **最佳化**屬性頁。

1. 修改**最佳化**屬性。

### <a name="to-set-this-compiler-option-programmatically"></a>若要以程式方式設定這個編譯器選項

- 請參閱 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>。

## <a name="see-also"></a>另請參閱

[/O 選項 (最佳化程式碼)](../../build/reference/o-options-optimize-code.md)<br/>
[編譯器選項](../../build/reference/compiler-options.md)<br/>
[設定編譯器選項](../../build/reference/setting-compiler-options.md)<br/>
[/Z7、/Zi、/ZI (偵錯資訊格式)](../../build/reference/z7-zi-zi-debug-information-format.md)