---
title: /validate-charset （驗證字元相容)
ms.date: 02/06/2019
f1_keywords:
- /validate-charset
- validate-charset
helpviewer_keywords:
- /validate-charset compiler option
ms.assetid: 50360fd0-4d32-4a4f-95d0-53d38c12ad4c
ms.openlocfilehash: 69b43b603ef4711e1acc0bd612e0e1c949722dc9
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850074"
---
# <a name="validate-charset-validate-for-compatible-characters"></a>/validate-charset （驗證字元相容)

驗證的原始程式檔文字只包含字元可表示為 utf-8。

## <a name="syntax"></a>語法

```
/validate-charset[-]
```

## <a name="remarks"></a>備註

您可以使用 **/validate-charset**選項，以驗證您的原始程式碼包含只可以用來表示這兩個來源字元集的字元設定和執行字元集。 這項檢查會自動啟用，當您指定 **/source-charset**， **/execution-charset**，或 **/utf-8**編譯器選項。 您可以藉由指定明確停用這項檢查 **/ 驗證-字元集-** 選項。

根據預設，Visual Studio 會偵測以判斷原始程式檔是否編碼的 Unicode 格式，例如 utf-16 或 utf-8 位元組順序標記。 如果找到沒有位元組順序標記，它就會假設來源檔案編碼使用目前使用者的字碼頁，除非您已使用指定的字碼頁 **/utf-8**或 **/source-charset**選項。 Visual Studio 可讓您使用數種字元編碼的任何儲存您的 c + + 程式碼。 來源和執行字元集的相關資訊，請參閱[字元集](../../cpp/character-sets.md)語言文件中。 一份支援的字碼頁識別項與設定名稱的字元，請參閱[字碼頁識別項](/windows/desktop/Intl/code-page-identifiers)。

Visual Studio 會使用 utf-8，做為原始程式碼字元集和執行字元集之間轉換時的內部字元編碼。 如果原始程式檔中的字元不能以執行字元集來表示，utf-8 轉換會以替代問號 '？ ' 字元。 **/Validate-charset**選項會使編譯發生這種情況時，回報警告。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 開發環境中設定這個編譯器選項

1. 開啟專案的 [ **屬性頁** ] 對話方塊。 如需詳細資訊，請參閱[使用專案屬性](../../ide/working-with-project-properties.md)。

1. 依序展開**組態屬性**， **C/c + +**，**命令列**資料夾。

1. 在 **其他選項**，新增 **/validate-charset**選項，並指定您慣用的編碼方式。

1. 選取 [確定] 儲存您的變更。

## <a name="see-also"></a>另請參閱

[編譯器選項](../../build/reference/compiler-options.md)<br/>
[設定編譯器選項](../../build/reference/setting-compiler-options.md)<br/>
[/execution-charset （設定執行字元集）](../../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/source-charset (設定來源字元集)](../../build/reference/source-charset-set-source-character-set.md)<br/>
[/utf-8 (將來源和可執行檔字元集設定為 UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)