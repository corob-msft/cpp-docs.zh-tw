---
title: ActiveX 控制項容器：將控制項插入控制項容器應用程式中
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX control containers [MFC], inserting controls
- ActiveX controls [MFC], adding to projects
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
ms.openlocfilehash: 2ca503119df955e8b76f6f8c131421f3e2d85652
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541371"
---
# <a name="activex-control-containers-inserting-a-control-into-a-control-container-application"></a>ActiveX 控制項容器：將控制項插入控制項容器應用程式中

您可以從 ActiveX 控制項容器應用程式來存取 ActiveX 控制項之前，您必須加入 ActiveX 控制項容器應用程式使用[插入 ActiveX 控制項](../windows/insert-activex-control-dialog-box.md) 對話方塊。

若要加入 ActiveX 控制項容器專案中的 ActiveX 控制項，請參閱[檢視及加入 ActiveX 控制項加入至對話方塊](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)。

當您新增控制項之後時，您需要將類型成員變數 （ActiveX 控制項） 加入至對話方塊類別。 如需有關此程序的詳細資訊，請參閱 <<c0> [ 加入成員變數](../ide/adding-a-member-variable-visual-cpp.md)。

一旦您加入成員變數的類別，稱為 「 包裝函式類別，自動產生及加入至專案。 這個類別做為控制項容器與內嵌的控制項之間的介面。

## <a name="see-also"></a>另請參閱

[ActiveX 控制項容器](../mfc/activex-control-containers.md)

