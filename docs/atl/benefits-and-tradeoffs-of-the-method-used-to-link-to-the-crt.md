---
title: 優點和權衡取捨，用來連結到 CRT 之方法
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: b4c91b7fe5182c8457d16de57792ba1b5ab7b3be
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496977"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>優點和權衡取捨，用來連結到 CRT 之方法

動態或靜態方式，您的專案可以連結到 crt。 下表概述的優點和權衡取捨中選擇要使用的方法。

|方法|優勢|權衡取捨|
|------------|-------------|--------------|
|以靜態方式連結到 CRT<br /><br /> (**執行階段程式庫**設為**單一執行緒**)|映像會執行的系統上不需要此 CRT DLL。|大約 25 K 的啟始程式碼會新增至您的映像，大幅增加其大小。|
|動態連結到 CRT<br /><br /> (**執行階段程式庫**設為**多執行緒**)|您的映像不需要的 CRT 啟始程式碼中，因此很遠。|CRT DLL 必須在執行映像的系統上。|

本主題[連結至您的 ATL 專案中的 CRT](../atl/linking-to-the-crt-in-your-atl-project.md)討論如何選取要連結到 CRT 的方式。

## <a name="see-also"></a>另請參閱

[使用 ATL 和 C 執行階段程式碼進行程式設計](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLL 和 Visual C++ 執行階段程式庫行為](../build/run-time-library-behavior.md)<br/>
[CRT 程式庫功能](../c-runtime-library/crt-library-features.md)

