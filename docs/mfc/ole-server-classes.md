---
title: "OLE 伺服器類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.ole
dev_langs: C++
helpviewer_keywords:
- OLE server applications [MFC], server classes
- OLE server documents
- COM components, classes [MFC]
- component classes [MFC]
ms.assetid: 8e9b67a2-c0ff-479c-a8d6-19b36c5e6fc6
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d23c7cb23d9221f8f2183c666a99c70ef149db3e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/21/2017
---
# <a name="ole-server-classes"></a>OLE 伺服器類別
伺服器應用程式會使用這些類別。 伺服器文件衍生自`COleServerDoc`而不是從**CDocument**。 請注意，因為`COleServerDoc`衍生自`COleLinkingDoc`，伺服器文件也可以支援連結的容器。  
  
 `COleServerItem`類別代表文件或其他文件中內嵌或連結至文件的一部分。  
  
 `COleIPFrameWnd`和`COleResizeBar`時，支援就地編輯的物件在容器中，和`COleTemplateServer`支援文件/檢視組的建立，因此可以編輯其他應用程式中的 OLE 物件。  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 做為伺服器應用程式文件類別的基底類別。 `COleServerDoc`物件提供的伺服器支援，透過與互動大量`COleServerItem`物件。 使用類別庫的文件/檢視架構來提供視覺化編輯的功能。  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 抽象基底類別的`COleClientItem`和`COleServerItem`。 物件的類別衍生自`CDocItem`代表文件的部分。  
  
 [COleServerItem](../mfc/reference/coleserveritem-class.md)  
 用來代表的 OLE 介面`COleServerDoc`項目。 有一個通常`COleServerDoc`物件，代表文件中內嵌的一部份。 在 支援的文件的組件的連結的伺服器，可以有許多`COleServerItem`物件，其中每一個代表文件部分的連結。  
  
 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)  
 當就地編輯伺服器文件時，則您可以提供檢視框架視窗。  
  
 [COleResizeBar](../mfc/reference/coleresizebar-class.md)  
 提供的標準使用者介面就地調整大小。 這個類別的物件一律使用搭配`COleIPFrameWnd`物件。  
  
 [COleTemplateServer](../mfc/reference/coletemplateserver-class.md)  
 用來建立使用架構的文件/檢視架構文件。 A`COleTemplateServer`物件會委派其工作相關聯的大部分`CDocTemplate`物件。  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 因 OLE 處理失敗而產生的例外狀況。 容器和伺服器都使用這個類別。  
  
## <a name="see-also"></a>請參閱  
 [類別概觀](../mfc/class-library-overview.md)
