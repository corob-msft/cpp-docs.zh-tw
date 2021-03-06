---
title: 加入、編輯或刪除控制項
ms.date: 11/04/2016
f1_keywords:
- vc.editors.dialog.dialog
- vc.controls.activex
- vc.editors.dialog.insertActiveXControls
helpviewer_keywords:
- Dialog Editor [C++], creating controls
- dialog boxes [C++], adding controls to
- Toolbox [C++], Dialog Editor tab
- controls [C++], types
- syslink controls in dialog boxes
- custom controls [C++], dialog boxes
- controls [C++], standard
- Dialog Editor [C++], creating controls
- controls [C++], adding to dialog boxes
- controls [C++], adding multiple
- dialog box controls [C++], size
- controls [C++], sizing
- dialog boxes [C++], adding ActiveX controls
- ActiveX controls [C++], adding to dialog boxes
- Insert ActiveX Control dialog box [C++]
- controls [C++], editing properties
- ActiveX controls [C++], properties
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
- dialog box controls [C++], deleting
- controls [C++], deleting
- Dialog Editor [C++], default control events
- controls [C++], default control events
- events [C++], controls
- dialog box controls [C++], events
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog Editor [C++], defining member variables for controls
ms.assetid: 73cef03f-5c8c-456a-87d1-1458dff185cf
ms.openlocfilehash: b4edb5b7a51e4f6d368759ebc2e05a1cc585f19a
ms.sourcegitcommit: 52c05e10b503e834c443ef11e7ca1987e332f876
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2019
ms.locfileid: "55742748"
---
# <a name="adding-editing-or-deleting-controls"></a>加入、編輯或刪除控制項

使用 **對話方塊**編輯器中，您可以新增、 調整大小、 編輯和刪除在對話方塊中的控制項。 您也可以編輯的控制項，例如其識別碼、 屬性或它是否一開始出現在執行階段。

**對話方塊編輯器**索引標籤會出現在[工具箱視窗](/visualstudio/ide/reference/toolbox)當您處理**對話方塊**編輯器。 您也可以自訂**工具箱**，方便使用的視窗。 如需詳細資訊，請參閱 <<c0> [ 使用工具列](/visualstudio/ide/using-the-toolbox)並[顯示或隱藏 [工具箱] 視窗](showing-or-hiding-the-dialog-editor-toolbar.md)。

您可以使用中的捷徑功能表** 對話方塊**編輯器快速加入登錄 ActiveX 控制項加入對話方塊中，而且您可以將 ActiveX 控制項加入**工具箱**快速存取。

中可用的標準控制項**工具箱**事件是預設值：

|控制項名稱|預設事件|
|---|---|
|[按鈕控制項](../mfc/reference/cbutton-class.md)|BN_CLICKED|
|[核取方塊控制項](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[下拉式方塊控制項](../mfc/reference/ccombobox-class.md)|CBN_SELCHANGE|
|[編輯控制項](../mfc/reference/cedit-class.md)|EN_CHANGE|
|群組方塊|（不適用）|
|[清單方塊控制項](../mfc/reference/clistbox-class.md)|LBN_SELCHANGE|
|[選項按鈕控制項](../mfc/reference/styles-used-by-mfc.md#button-styles)|BN_CLICKED|
|[靜態文字控制項](../mfc/reference/cstatic-class.md)|（不適用）|
|[圖片控制項](../mfc/reference/cpictureholder-class.md)|（不適用）|
|[Rich Edit 2.0 控制項](../mfc/using-cricheditctrl.md)|EN_CHANGE|
|[捲軸控制項](../mfc/reference/cscrollbar-class.md)|NM_THEMECHANGED|

如需有關使用**RichEdit 1.0**控制項與 MFC，請參閱[使用 RichEdit 1.0 控制項與 MFC](../windows/using-the-richedit-1-0-control-with-mfc.md)並[豐富編輯控制項範例](../mfc/rich-edit-control-examples.md)。

[Windows 通用控制項](../mfc/controls-mfc.md)中可用**工具箱**提供增強的功能，在您的應用程式。 包括：

|控制項名稱|預設事件|
|---|---|
|[滑桿控制項](../mfc/slider-control-styles.md)|NM_CUSTOMDRAW|
|[微調控制項](../mfc/using-cspinbuttonctrl.md)|UDN_DELTAPOS|
|[進度控制項](../mfc/styles-for-the-progress-control.md)|NM_CUSTOMDRAW|
|[熱鍵控制項](../mfc/using-a-hot-key-control.md)|NM_OUTOFMEMORY|
|[清單控制項](../mfc/list-control-and-list-view.md)|LVN_ITEMCHANGE|
|[樹狀目錄控制項](../mfc/tree-control-styles.md)|TVN_SELCHANGE|
|[索引標籤控制項](../mfc/tab-controls-and-property-sheets.md)|TCN_SELCHANGE|
|[動畫控制項](../mfc/using-an-animation-control.md)|ACN_START|
|[日期時間選擇器控制項](../mfc/creating-the-date-and-time-picker-control.md)|DTN_DATETIMECHANGE|
|[月曆控制項](../mfc/month-calendar-control-examples.md)|MCN_SELCHANGE|
|[IP 位址控制項](../mfc/reference/cipaddressctrl-class.md)|IPN_FIELDCHANGED|
|[擴充的下拉式方塊控制項](../mfc/creating-an-extended-combo-box-control.md)||
|[自訂控制項](custom-controls-in-the-dialog-editor.md)|TTN_GETDISPINFO|

如需詳細資訊，請參閱 <<c0> [ 控制項類別](../mfc/control-classes.md)，[對話方塊類別](../mfc/dialog-box-classes.md)，並[捲軸樣式](../mfc/reference/styles-used-by-mfc.md#scroll-bar-styles)。

如需將資源加入 managed 專案的詳細資訊，請參閱[Resources in Desktop Apps](/dotnet/framework/resources/index)中 *.NET Framework 開發人員指南*。 如需手動將資源檔加入 managed 專案、 存取資源、 顯示靜態資源及指派資源字串給屬性的資訊，請參閱[建立桌面應用程式的資源檔](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)。 全球化和當地語系化的受管理的應用程式中的資源上的資訊，請參閱[全球化和當地語系化.NET Framework 應用程式](/dotnet/standard/globalization-localization/index)。

## <a name="to-add-a-control"></a>若要加入控制項

若要將控制項加入新的對話方塊中，將控制項從**工具箱**到您要建立的對話方塊。 然後移動控制項，或變更其大小和形狀。

您可以將自訂控制項加入對話方塊中選取**自訂控制項**中的圖示**工具箱**將它拖曳至您的對話方塊。 若要新增**Syslink**控制項，加入自訂控制項，然後變更控制項的**類別**屬性設**Syslink**。 此動作會導致要重新整理和顯示的屬性**Syslink**控制屬性。 如需 MFC 包裝函式類別的資訊，請參閱[CLinkCtrl](../mfc/reference/clinkctrl-class.md)。

### <a name="to-add-a-control-to-a-dialog-box"></a>在對話方塊加入控制項

1. 確定對話方塊索引標籤式視窗是編輯器框架中的目前文件。 如果對話方塊不是目前的文件，您不會看到**對話方塊編輯器索引標籤**中**工具箱**。

1. 在 [**對話方塊編輯器**索引標籤**工具箱**] 視窗中，選取您想要的控制項，然後：

   選取您想要將控制項放置位置的對話方塊。 控制項中，就會出現您所選取的位置。

   \-或-

   將拖放控制項**工具箱**視窗至您的對話方塊上的位置。

   \-或-

   按兩下中的控制項**工具箱**（出現在您的對話方塊） 視窗，然後重新定位控制項以您偏好的位置。

### <a name="to-add-multiple-controls"></a>若要將多個控制項

1. 按住**Ctrl**機碼，請選取中的控制項**工具箱**視窗。

1. 發行**Ctrl**鍵並選取 [] 對話方塊中，您想要新增之特定控制項的次數。

1. 按下**Esc**來停止放置控制項。

### <a name="to-size-a-control-while-you-add-it"></a>若要調整控制項的大小，而您將它加入

1. 選取的控制項**工具箱**視窗。

1. 將游標放 （這會顯示當十字） 您想要在您的對話方塊上的新控制項的左上角的位置。

1. 選取並按住滑鼠按鈕，即可在對話方塊中，控制項的左上角的錨點，然後將游標拖曳至右和向下直到控制項是您想要的大小。

   > [!NOTE]
   > 您可以實際上錨定在任何您正在繪製之控制項的四個邊角。 此程序會使用左上角，做為範例。

1. 放開滑鼠按鈕。 控制項置於對話方塊中，您所指定的大小。

   > [!TIP]
   > 您可以調整控制項的大小之後它拖放到對話方塊中移動控制項框線的縮放控點。 如需詳細資訊，請參閱 <<c0> [ 調整個別控制項](../windows/sizing-individual-controls.md)。

### <a name="to-add-an-activex-control"></a>若要加入 ActiveX 控制項

Visual Studio 可讓您在您的對話方塊中插入 ActiveX 控制項。 如需詳細資訊，請參閱 < [MFC ActiveX 控制項](../mfc/mfc-activex-controls.md)並[ActiveX 控制項容器](../mfc/activex-control-containers.md)。

**插入 ActiveX 控制項**對話方塊可讓您插入您的對話方塊中的 ActiveX 控制項，同時使用[對話方塊編輯器](../windows/dialog-editor.md)。 此對話方塊包含下列屬性：

|屬性|描述|
|---|---|
|**ActiveX 控制項**|會顯示一份 Active X 控制項。 從這個對話方塊中插入控制項不會產生包裝函式類別。 如果您需要的包裝函數類別，使用[類別檢視](/visualstudio/ide/viewing-the-structure-of-code)若要建立一個 (如需詳細資訊，請參閱[加入類別](../ide/adding-a-class-visual-cpp.md))。 如果 Active X 控制項不會出現在這個對話方塊中，再次嘗試安裝控制項根據廠商的指示。|
|**路徑**|顯示 ActiveX 控制項所在的檔案。|

#### <a name="to-see-the-activex-controls-available"></a>若要查看可用的 ActiveX 控制項

1. 在 [對話方塊] 編輯器中開啟對話方塊。

1. 以滑鼠右鍵按一下任何位置 對話方塊中的主體中。

1. 在快速鍵功能表中，選取**插入 ActiveX 控制項**。

   **插入 ActiveX 控制項** 對話方塊隨即出現，顯示您系統上的所有 ActiveX 控制項。 ActiveX 控制項檔案的路徑會顯示在對話方塊的底部。

#### <a name="to-add-an-activex-control-to-a-dialog-box"></a>在對話方塊中加入 ActiveX 控制項

1. 在 **插入 ActiveX 控制項**對話方塊方塊中，選取您想要新增到您的對話方塊中，然後選取的控制**確定**。

   該控制項會出現在對話方塊中。您可以像處理其他控制項般地加以編輯，或為其建立處理常式。

   > [!NOTE]
   > 您可以將 ActiveX 控制項加入**工具箱**視窗以方便存取。

   > [!CAUTION]
   > 在您的系統上散發所有的 ActiveX 控制項可能不合法。 請參閱安裝這些控制項之軟體的授權合約，或連絡軟體公司。

## <a name="to-edit-a-control"></a>若要編輯的控制項

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>若要編輯的控制項或控制項屬性

1. 在對話方塊中，選取您想要修改的控制項。

   > [!NOTE]
   > 如果您選取多個控制項時，就可以編輯只有選取的控制項通用的屬性。

1. 在 [[屬性] 視窗](/visualstudio/ide/reference/properties-window)，變更您的控制項的屬性。

   > [!NOTE]
   > 當您設定**點陣圖**按鈕、 選項按鈕或等於的核取方塊控制項內容 **，則為 True**，為您的控制項實作 BS_BITMAP 樣式。 如需詳細資訊，請參閱 <<c0> [ 按鈕樣式](../mfc/reference/styles-used-by-mfc.md#button-styles)。 如需範例的關聯控制項的點陣圖，請參閱[CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap)。 點陣圖不會出現在您的控制項中 **對話方塊**資源編輯器。

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>若要復原變更控制項的屬性

1. 請確定且焦點在控制項 **對話方塊**編輯器。

1. 選擇**恢復**從**編輯**功能表 (如果焦點在控制項上，不**復原**命令將會無法使用)。

### <a name="to-edit-properties-for-an-activex-control"></a>若要編輯 ActiveX 控制項的屬性

獨立廠商所提供的 ActiveX 控制項可能都配有其自己的屬性和特性的。 適用於 ActiveX 控制項的屬性會顯示在**屬性**視窗。 此外，ActiveX 控制項的寫入器所建立的任何屬性頁面會顯示在**屬性頁** 對話方塊 (若要檢視** 屬性頁**對於特定的 ActiveX 控制項中，按一下 ** 屬性頁**按鈕[屬性 視窗](/visualstudio/ide/reference/properties-window))。

各種索引標籤會顯示在屬性頁面中的 ActiveX 控制項，視屬性工作表做為 ActiveX 控制項的一部分，而定。

> [!NOTE]
> 下列程序適用於使用屬性頁編輯 ActiveX 控制項。 您也可以瀏覽並編輯 ActiveX 屬性中的新**屬性**視窗。

1. 選取  **ActiveX**控制項。

1. 在上**檢視**功能表上，選取** 屬性頁**檢視內容。

1. 視需要在 [屬性] 頁面中，請進行變更。

### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>定義對話方塊控制項的成員變數 (非按鈕)

若要定義任何對話方塊控制項 (按鈕除外) 的成員變數，您可以使用下列方法。

> [!NOTE]
> 此程序只適用於 MFC 專案中的對話方塊控制項。 ATL 專案應使用**新的 Windows 訊息和事件處理常式** 對話方塊。 如需詳細資訊，請參閱 <<c0> [ 使用者介面物件與相關聯的訊息類型](../mfc/reference/message-types-associated-with-user-interface-objects.md)，[編輯訊息處理常式](../mfc/reference/editing-a-message-handler.md)，和[訊息處理常式定義反映訊息](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).

1. 在 [對話方塊編輯器](../windows/dialog-editor.md)，在選取的控制項。

1. 同時按下**Ctrl**機碼，請按兩下對話方塊控制項。

   [加入成員變數精靈](../ide/add-member-variable-wizard.md)隨即出現。

1. 輸入中的相關資訊**加入成員變數**精靈。 如需詳細資訊，請參閱 <<c0> [ 對話資料交換](../mfc/dialog-data-exchange.md)。

1. 選取  **確定**以返回**對話方塊**編輯器。

   > [!TIP]
   > 若要從任何對話方塊控制項跳至其現有的處理常式，請按兩下控制項。

您也可以使用**成員變數**索引標籤中[MFC 類別精靈](../mfc/reference/mfc-class-wizard.md)，新增新的成員變數，指定的類別，並檢視已定義的成員變數。

## <a name="to-delete-a-control"></a>若要刪除控制項

在對話方塊中，選取 控制項，然後按**刪除**索引鍵。

   \-或-

在 **編輯**功能表上，選取**刪除**。

   > [!TIP]
   > 在使用時 **對話方塊**編輯器，在許多情況下，您可以按一下滑鼠右鍵顯示常用命令的捷徑功能表。

## <a name="requirements"></a>需求

Win32

## <a name="see-also"></a>另請參閱

[對話方塊中的控制項](controls-in-dialog-boxes.md)<br/>
[對話方塊控制項和變數類型](../ide/dialog-box-controls-and-variable-types.md)<br/>
[資源檔](../windows/resource-files-visual-studio.md)<br/>

<!-- excluded links
[Mapping Messages to Functions](../mfc/reference/mapping-messages-to-functions.md)<br/>
[Adding Functionality with Code Wizards](../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Adding a Class](../ide/adding-a-class-visual-cpp.md)<br/>
[Adding a Member Function](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Overriding a Virtual Function](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler](../mfc/reference/adding-an-mfc-message-handler.md)
[Declaring a Variable Based on Your New Control Class](../mfc/reference/declaring-a-variable-based-on-your-new-control-class.md)<br/>
-->
