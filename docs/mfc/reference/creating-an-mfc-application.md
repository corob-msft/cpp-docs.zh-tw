---
title: 建立 MFC 應用程式
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC]
- MFC, creating applications
- MFC applications
ms.assetid: b8b8aa08-9c49-404c-8078-b42079ac18f0
ms.openlocfilehash: df1e49ffe9e4350d2023bc471d3687bec5defa04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50434602"
---
# <a name="creating-an-mfc-application"></a>建立 MFC 應用程式

MFC 應用程式以 MFC 程式庫為基礎，是 Windows 的可執行應用程式。 要建立 MFC 應用程式，最簡單的方法就是使用 MFC 應用程式精靈。

> [!IMPORTANT]
>  Visual Studio Express 版本不支援 MFC 專案。

MFC 可執行檔一般分為五種類型： 標準的 Windows 應用程式、 對話方塊、 表單架構應用程式、 檔案總管樣式應用程式和 Web 瀏覽器型應用程式。 如需詳細資訊，請參閱:

- [使用類別來撰寫 Windows 應用程式](../../mfc/using-the-classes-to-write-applications-for-windows.md)

- [建立和顯示對話方塊](../../mfc/creating-and-displaying-dialog-boxes.md)

- [建立表單架構的 MFC 應用程式](../../mfc/reference/creating-a-forms-based-mfc-application.md)

- [建立檔案總管樣式的 MFC 應用程式](../../mfc/reference/creating-a-file-explorer-style-mfc-application.md)

- [建立網頁瀏覽器樣式的 MFC 應用程式](../../mfc/reference/creating-a-web-browser-style-mfc-application.md)

MFC 應用程式精靈可根據您在精靈中選取的選項，為任意類型的應用程式，產生適當的類別和檔案。

### <a name="to-create-an-mfc-application-using-the-mfc-application-wizard"></a>若要使用 MFC 應用程式精靈建立 MFC 應用程式

1. 請遵循說明主題[使用 Visual C++ 應用程式精靈建立專案](../../ide/creating-desktop-projects-by-using-application-wizards.md)中的指示操作。

1. 在 **新的專案**對話方塊中，選取**MFC 應用程式**以開啟精靈的 範本 窗格中。

1. 定義使用的應用程式設定[MFC 應用程式精靈](../../mfc/reference/mfc-application-wizard.md)。

    > [!NOTE]
    >  若要保留精靈的預設值，請略過此步驟。

1. 按一下 **完成**以關閉精靈，並在開發環境中開啟新專案。

您的專案建立之後，您可以檢視中建立的檔案**方案總管 中**。 如需精靈建立之專案檔案的詳細資訊，請參閱專案所產生的 ReadMe.txt 檔案。 如需檔案類型的詳細資訊，請參閱[Visual c + + 專案建立的檔案類型](../../ide/file-types-created-for-visual-cpp-projects.md)。

## <a name="see-also"></a>另請參閱

[使用程式碼精靈新增功能](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[屬性頁](../../ide/property-pages-visual-cpp.md)

