---
title: 在框架視窗中拖放檔案
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
ms.openlocfilehash: 34fb6ec6d57bcf8bc1cf51a3ac0c0db5203b3ffa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498818"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>在框架視窗中拖放檔案

框架視窗會管理與檔案總管或檔案管理員的關聯性。

藉由新增數個初始化呼叫中的覆寫`CWinApp`成員函式`InitInstance`所述，在[CWinApp： 應用程式類別](../mfc/cwinapp-the-application-class.md)，您可以讓您以間接開啟檔案從檔案的框架視窗總管或檔案管理員並且放置在框架視窗。 請參閱[檔案管理員拖放](../mfc/special-cwinapp-services.md)。

## <a name="see-also"></a>另請參閱

[使用框架視窗](../mfc/using-frame-windows.md)

