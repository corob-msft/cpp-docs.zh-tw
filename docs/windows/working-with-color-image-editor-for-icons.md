---
title: 使用色彩 (圖示影像編輯器)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.image.color
- vc.editors.customcolorselector
- vc.editors.loadcolorpalette
- vc.editors.colorswindow
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors [C++], Image editor
- colors [C++]
- Image editor [C++], colors
- colors [C++], Image editor
- colors [C++], image
- images [C++], colors
- Image editor [C++], colors
- Fill tool
- colors [C++], image
- images [C++], colors
- colors [C++], selection tools
- Image editor [C++], colors
- Select Color tool
- dithered color, Image editor
- Custom Color Selector dialog box [C++]
- Image editor [C++], Colors Palette
- colors [C++], image
- bitmaps [C++], colors
- images [C++], colors
- HSL values
- Colors Palette, Image editor
- RGB color values
- Adjust Colors command [C++]
- Image editor [C++], dithered color
- Image editor [C++], Colors Palette
- Colors Palette, Image editor
- colors [C++], inverting
- colors [C++]
- Color Indicator
- colors [C++], Colors window
- Colors window, hiding colors
- Show Colors Window command
- Colors window, displaying colors
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
- color palettes
- Load Palette Colors dialog box [C++]
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
- colors [C++], image
- Image editor [C++], color inversion
- images [C++], colors
- colors [C++], inverting
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
ms.openlocfilehash: f2ac2cf7eaab0372b9cf349e1544fc5b3426dee6
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850363"
---
# <a name="working-with-color-image-editor-for-icons"></a>使用色彩 (圖示影像編輯器)

**影像編輯器**包含許多功能，特別是處理和自訂色彩。 您可以設定前景或背景色彩、 繫結的區域填滿色彩，或選取要做為目前的前景或背景色彩的影像上的色彩。 您可以使用上的工具[影像編輯器 工具列](../windows/toolbar-image-editor-for-icons.md)以及中的色彩調色盤**色彩**視窗建立映像。

所有的色彩，單色和 16 色影像所示**色彩**中的調色盤**色彩**視窗。 16 個標準色彩，以及您可以建立您自己自訂的色彩。 色彩調色盤中的任何變更會立即變更映像中對應的色彩。

當使用 256 色圖示和游標影像**色彩**中的屬性[屬性 視窗](/visualstudio/ide/reference/properties-window)用。 如需詳細資訊，請參閱 <<c0> [ 建立 256 色圖示或游標](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md)。

> [!NOTE]
> 使用**影像編輯器**，您可以檢視 32 位元映像，但無法加以編輯。

也可以建立全彩映像。 不過，則為 true 的色彩範例不會出現在中的完整調色盤**色彩**視窗; 它們只會出現在前景或背景色彩指示器區域。 使用所建立，則為 true 的色彩[自訂色彩選取器對話方塊](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)。

您可以儲存在磁碟上的 自訂的色彩調色盤，並視需要重新載入。 您最近使用的色彩調色盤會儲存在登錄中，並自動載入 下一次啟動 Visual Studio。

## <a name="select-foreground-or-background-colors"></a>選取前景或背景色彩

除了**橡皮擦**，在工具**影像編輯器**工具列繪製以目前前景或背景色彩時您分別按滑鼠左鍵或右鍵。

### <a name="to-select-a-foreground-color"></a>選取前景色彩

使用滑鼠左鍵，選取 您想要的色彩**色彩**調色盤。

### <a name="to-select-a-background-color"></a>選取背景色彩

以滑鼠右鍵，選取您想要在的色彩**色彩**調色盤。

## <a name="filling-a-bounded-area-of-an-image-with-a-color"></a>以色彩填滿影像的封閉區域

影像編輯器可**填滿**工具以便填滿任何包含與目前的繪圖色彩或目前的背景色彩的影像區域。

> [!TIP]
> 將游標停留在工具列按鈕時，就會出現工具提示。 這些提示可協助您識別每個按鈕的功能。

### <a name="to-use-the-fill-tool"></a>若要使用的填滿工具

1. 上**影像編輯器**工具列 (或**映像**功能表**工具**命令)，選取**填滿**工具。

1. 如有必要，可選擇繪圖色彩：在 [色彩調色盤](../windows/colors-window-image-editor-for-icons.md)，選取 選取前景色彩的滑鼠左的按鈕或滑鼠右鍵以選取 背景色彩。

1. 移動**填滿**工具，以您想要填滿的區域。

1. 選取左邊或右邊的滑鼠按鈕，即可分別使用的前景色彩或背景色彩填滿。

## <a name="pick-up-a-color-from-an-image-to-use-elsewhere"></a>挑選其他位置使用的映像中的色彩

**選取色彩**，或色彩揀選工具建立映像上的任何色彩背景色彩，取決於您按左或右滑鼠按鍵的目前的前景色彩。 若要取消**選取色彩**工具，請選擇另一個工具。

> [!TIP]
> 將游標停留在工具列按鈕時，就會出現工具提示。 這些提示可協助您識別每個按鈕的功能。

### <a name="to-pick-up-a-color"></a>挑選色彩

1. 上**影像編輯器**工具列 (或從**映像**功能表**工具**命令)，選取**選取色彩**工具。

1. 選取您想要從映像中挑選的色彩。

   > [!NOTE]
   > 您挑選一種色彩之後,**映像**編輯器予以最近使用的工具。

1. 繪製前景色彩，或滑鼠右按鈕的背景色彩，使用滑鼠左鍵。

## <a name="choose-a-transparent-or-opaque-background"></a>選擇透明或不透明背景

當您移動或複製的選取項目，從映像時，任何像素選取範圍中符合目前的背景色彩的是，根據預設，透明，它們不會遮住的目標位置中的像素為單位。

您可以從透明背景 （預設值） 的不透明背景，來回切換。 當您使用選項工具 中，**透明背景**並**不透明的背景**選項會出現在**選項**上的選取器**影像編輯器**工具列 （如下所示）。

![背景選項&#45;不透明或透明](../windows/media/vcimageeditoropaqtranspback.gif "背景選項&#45;不透明或透明")<br/>
**透明及不透明的選項**上**影像編輯器工具列**

### <a name="to-switch-between-a-transparent-and-opaque-background"></a>若要切換透明及不透明背景

在 **影像編輯器**工具列上，選取**選項**選取器，然後選擇適當的背景：

   - `Opaque Background (O)`：現有的映像會隱藏的選取範圍的所有組件。

   - `Transparent Background (T)`：現有的映像會顯示符合目前的背景色彩選取範圍的組件。

   \-或-

在 **映像**功能表上，選取或清除**繪製不透明**。

當選取範圍已變更影像的哪些部分而言是透明的作用中時，您可以變更背景色彩。

## <a name="invert-the-colors-in-a-selection"></a>在 選取範圍色彩對換

**映像**編輯器提供便利的方式，可反轉選取的映像的組件中的色彩，讓您知道映像會如何顯示以反轉的色彩。

### <a name="to-invert-colors-in-the-current-selection"></a>反轉目前選取範圍中的色彩

在 **映像**功能表上，選取**色彩對換**。

## <a name="customize-or-change-colors"></a>自訂或變更色彩

**映像**編者**色彩**調色盤一開始會顯示 16 個標準色彩。 顯示色彩，您也可以建立您自己自訂的色彩。 您可以接著[儲存及載入自訂的調色盤](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)。

**自訂色彩選取器**對話方塊可讓您自訂映像您使用的色彩。 會包含下列屬性：

|屬性|描述|
|--------------------------|--------------------------|
|**漸層色彩顯示**|變更所選取之色彩的值。 您想要變更的位置是色彩十字形狀。 然後移動滑桿向上或向下變更的明暗度或色彩的 RGB 值。|
|**亮度列**|設定您在中選取之色彩的亮度**漸層色彩顯示** 方塊中。 選取並拖曳白色箭號，更高的亮度列向上或向下的鍵小於。 **色彩**方塊會顯示您所選取的色彩和您所設定的明暗度的效果。|
|**Color**|列出您要定義之色彩的色調 （色彩轉輪值）。 值範圍從 0 到 240，其中 0 是紅色、 60 是黃色，120 是綠色、 180 是青色、 200 表示 「 洋紅、 240 是藍色。|
|**Hue**|列出您要定義之色彩的色調 （色彩轉輪值）。 值範圍從 0 到 240，其中 0 是紅色、 60 是黃色，120 是綠色、 180 是青色、 200 表示 「 洋紅、 240 是藍色。|
|**Sat**|指定您要定義之色彩的濃度值。 飽和度是色彩的在指定的色調量。 值範圍從 0 到 240。|
|**Lum**|列出您要定義之色彩的亮度 （亮度）。 值範圍從 0 到 240。|
|**紅色**|指定您要定義之色彩的紅色值。 值範圍從 0 到 255 之間。|
|**綠色**|指定您要定義之色彩的綠色值。 值範圍從 0 到 255 之間。|
|**Blue**|指定您要定義之色彩的藍色值。 值範圍從 0 到 255 之間。|

### <a name="to-change-colors-on-the-colors-palette"></a>變更調色盤上的色彩

1. 從**映像**功能表上，選擇**調整色彩**。

1. 在 [**自訂色彩選取器**對話方塊方塊中，適當的文字方塊中輸入 RGB 或 HSL 值定義的色彩或選擇在色彩**漸層色彩顯示**] 方塊中。

1. 移動滑桿，以設定光度**亮度**列。

1. 許多自訂色彩會被遞色。 如果您想最接近遞色色彩的純色，按兩下**色彩** 方塊中。

   如果您稍後決定要遞色的色彩，移動滑桿**亮度**列，或移動中的交叉線**漸層色彩顯示**方塊，再以還原遞色。

1. 選取 **確定**若要新增新的色彩。

## <a name="save-and-load-different-color-palettes"></a>儲存及載入不同的色彩調色盤

您可以儲存及載入**色彩**包含自訂的色彩的色板。 (根據預設，**色彩**啟動 Visual Studio 時，會自動載入最近使用的調色盤。)

> [!TIP]
> 由於**映像**編輯器沒有任何方法來還原預設**色彩**調色盤，您應該儲存預設**色彩**調色盤的名稱，例如*以 standard.pal*或是*default.pal*以便您可以輕易地還原預設設定。

使用 **載入調色盤色彩**載入特殊的調色盤，以便在 c + + 專案中使用的對話方塊。 會包含下列屬性：

|屬性|描述|
|-----------------|-----------------|
|**查看**|指定您想要用來尋找檔案或資料夾的位置。 選取箭頭以選擇其他位置，或選取 [移至上一層] 工具列上的資料夾圖示。|
|**檔案名稱**|提供空間讓您輸入您想要開啟的檔案名稱。 若要快速尋找您先前已開啟的檔案，如果有的話，在下拉式清單中，選取的檔案名稱。<br/><br/>如果您要搜尋的檔案，您可以使用星號 （*） 做為萬用字元。 例如，您可以輸入\*。\*以查看所有檔案的清單。 您也可以輸入檔案，比方說，C:\My Documents\MyColorPalette.pal 的完整路徑或\\\NetworkServer\MyFolder\MyColorPalette.pal。|
|**檔案類型**|列出要顯示檔案的類型。 調色盤 (*.pal) 是預設的檔案類型的色彩調色盤。|

### <a name="to-save-a-custom-colors-palette"></a>若要儲存自訂色彩調色盤

1. 從**映像**功能表上，選擇**儲存調色盤**。

1. 瀏覽至您要儲存調色盤的目錄，然後輸入調色盤的名稱。

1. 選取 [儲存]。

### <a name="to-load-a-custom-colors-palette"></a>若要載入自訂色彩調色盤

1. 從**映像**功能表上，選擇**載入調色盤**。

1. 在 **載入色彩調色盤**對話方塊方塊中，瀏覽至正確的目錄，然後選取您想要載入的調色盤。 **色彩**調色盤會以.pal 副檔名儲存。

## <a name="colors-window"></a>色彩視窗

**色彩**視窗有兩個部分：

- **色彩調色盤**，即表示您可以使用的色彩的色彩範例陣列。 您可以選取當您使用圖形工具，請選擇前景和背景色彩的範例。

- **色彩指示器**，其中顯示的前景和背景色彩和螢幕及反向色彩選取器。

   ![色彩視窗](../windows/media/vccolorswindow.gif "vcColorsWindow")<br/>
   色彩視窗

> [!NOTE]
> **螢幕色彩**並**反向色彩**工具僅適用於圖示和游標。

您可以使用**色彩**視窗，其中[影像編輯器工具列](../windows/toolbar-image-editor-for-icons.md)。

### <a name="to-display-the-colors-window"></a>若要顯示色彩視窗

以滑鼠右鍵按一下**影像編輯器**窗格，然後選擇**顯示色彩視窗**從捷徑功能表。

   \-或-

選取 **顯示色彩視窗**上[影像功能表](../windows/image-menu-image-editor-for-icons.md)。

### <a name="to-hide-the-colors-window"></a>若要隱藏色彩視窗

取消釘選 視窗。 不在使用時，此動作將允許自動隱藏視窗。

\-或-

選取 [**關閉**] 按鈕。

如需將資源加入 managed 專案的詳細資訊，請參閱[Resources in Desktop Apps](/dotnet/framework/resources/index)中 *.NET Framework 開發人員指南*。 如需手動將資源檔加入 managed 專案、 存取資源、 顯示靜態資源及指派資源字串給屬性的資訊，請參閱[建立桌面應用程式的資源檔](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和當地語系化的受管理的應用程式中的資源上的資訊，請參閱[全球化和當地語系化.NET Framework 應用程式](/dotnet/standard/globalization-localization/index)。

## <a name="requirements"></a>需求

無

## <a name="see-also"></a>另請參閱

[快速鍵](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[在裝置影像中建立透明或反向區域](../windows/creating-transparent-or-inverse-regions-in-device-images.md)<br/>
[自訂色彩選取器對話方塊](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)<br/>
[圖示影像編輯器](../windows/image-editor-for-icons.md)<br/>
[影像功能表](../windows/image-menu-image-editor-for-icons.md)<br/>
