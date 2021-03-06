---
title: 影像功能表 （c + + 圖示影像編輯器）
ms.date: 11/04/2016
f1_keywords:
- vc.editors.bitmap
- vc.editors.dialog.GridSettings
- vc.editors.gridsettings
helpviewer_keywords:
- Image menu
- Grid Settings dialog box [C++]
ms.assetid: ac2b4d53-1919-4fd1-a0af-d3c085c45af2
ms.openlocfilehash: e7d7d92401d5910cbb8aba8ab4c6000eca45cb01
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849726"
---
# <a name="image-menu-c-image-editor-for-icons"></a>影像功能表 （c + + 圖示影像編輯器）

**映像**時才會顯示功能表**映像**編輯器之後，有可用於編輯映像的色板，和設定的命令**影像編輯器**視窗選項。 此外，使用裝置映像的命令可使用圖示和游標時。

|命令|描述|
|---|---|
|**色彩對換**|反轉色彩。 如需詳細資訊，請參閱 <<c0> [ 反轉選取範圍內的色彩](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)。|
|**水平翻轉**|水平翻轉影像或選取範圍。 如需詳細資訊，請參閱 <<c0> [ 翻轉影像](../windows/flipping-an-image-image-editor-for-icons.md)。|
|**垂直翻轉**|垂直翻轉影像或選取範圍。 如需詳細資訊，請參閱 <<c0> [ 翻轉影像](../windows/flipping-an-image-image-editor-for-icons.md)。|
|**旋轉 90 度**|旋轉影像或選取範圍 90 度。 如需詳細資訊，請參閱 <<c0> [ 翻轉影像](../windows/flipping-an-image-image-editor-for-icons.md)。|
|**顯示色彩視窗**|會開啟[色彩視窗](../windows/colors-window-image-editor-for-icons.md)，在您可以選擇要使用映像的色彩。 如需詳細資訊，請參閱 <<c0> [ 使用色彩](../windows/working-with-color-image-editor-for-icons.md)。|
|**將選取範圍當做筆刷**|可讓您建立自訂筆刷從映像的一部分。 您的選取項目會成為自訂筆刷可將選取範圍中的色彩分散到映像。 選取範圍的複本會保留在拖曳的路徑。 您將拖曳的速度變慢，進行更多的複本。 如需詳細資訊，請參閱 <<c0> [ 建立自訂筆刷](../windows/creating-a-custom-brush-image-editor-for-icons.md)。|
|**複製和外框的選取項目**|建立一份目前選取範圍的複本，並建立此複本的外框。 如果目前的選取範圍中包含的背景色彩，將不會包含如果您已經[透明](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)選取。
|**調整色彩**|會開啟[自訂色彩選取器](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md)，可讓您自訂映像您使用的色彩。 如需詳細資訊，請參閱 <<c0> [ 自訂或變更色彩](../windows/customizing-or-changing-colors-image-editor-for-icons.md)。|
|**載入調色盤**|會開啟[載入色彩調色盤對話方塊](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md)，可讓您載入先前儲存到.pal 檔案的調色盤色彩。|
|**儲存調色盤**|將儲存色板色彩.pal 檔案。|
|**繪製不透明**|選取時，會使目前的選取範圍不透明。 清除時，讓目前的選取範圍透明化。 如需詳細資訊，請參閱 <<c0> [ 選擇不透明或透明背景](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)。|
|**工具列編輯器**|會開啟[新增工具列資源對話方塊](../windows/new-toolbar-resource-dialog-box.md)。|
|**格線設定**|會開啟**格線設定**對話方塊中，您可以在此指定映像的方格。|
|**新的映像類型**|會開啟[的新\<裝置 > 影像類型對話方塊](../windows/new-device-image-type-dialog-box-image-editor-for-icons.md)。 單一的圖示資源可以包含不同大小的數個映像和 windows 可以使用適當的圖示大小取決於要如何顯示。 新的裝置類型不會修改大小的圖示，但而是會建立新的映像中的圖示。 僅適用於圖示和游標。|
|**目前的圖示/游標影像類型**|會開啟子功能表會列出第一個可用資料指標或圖示的映像 （第九個）。 在子功能表上的最後一個命令**更多...**，開啟[開放\<裝置 > 影像對話方塊](../windows/open-device-image-dialog-box-image-editor-for-icons.md)。|
|**刪除映像類型**|刪除選取的裝置映像。|
|**工具**|啟動子功能表，其中包含從提供的所有工具[影像編輯器工具列](../windows/toolbar-image-editor-for-icons.md)。|

**格線設定**對話方塊可讓您指定格線設定映像，並顯示格線內編輯影像。 格線可用於編輯映像，但不會儲存為映像本身的一部分。

|屬性|描述|
|---|---|
|**像素格線**|有選取時，會顯示有關每個像素格線，影像編輯器中。 方格會出現只在 4 × 和較高的解析度。|
|**磚狀格線**|選取時，顯示一個方格，周圍的像素為單位的區塊在影像編輯器中，格線間距值所指定。|
|[寬度]|指定每個圖格區塊的寬度。 繪製點陣圖包含定期排列的多個映像時，此屬性相當實用。|
|[高度]|指定每個圖格區塊的高度。 繪製點陣圖包含定期排列的多個映像時，此屬性相當實用。|

## <a name="requirements"></a>需求

無

## <a name="see-also"></a>另請參閱

[快速鍵](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[調整影像大小](../windows/resizing-an-image-image-editor-for-icons.md)<br/>
[圖示影像編輯器](../windows/image-editor-for-icons.md)