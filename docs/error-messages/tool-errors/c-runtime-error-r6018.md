---
title: C 執行階段錯誤 R6018
ms.date: 11/04/2016
f1_keywords:
- R6018
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
ms.openlocfilehash: e0d229b4fd8c1a4f8e067c0e59a278344fd4e113
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531909"
---
# <a name="c-runtime-error-r6018"></a>C 執行階段錯誤 R6018

未預期的堆積錯誤

> [!NOTE]
> 如果您遇到這個錯誤訊息時執行應用程式時，應用程式已關閉發生內部問題。 有幾個可能的原因，這個錯誤，但通常出自於應用程式的程式碼的缺失。
>
> 您可以嘗試進行下列步驟來修正這個錯誤：
>
> - 使用**應用程式和功能**或是**程式和功能**頁面**控制台**修復或重新安裝程式。
> - 請檢查**Windows Update**中**控制台**軟體更新。
> - 檢查應用程式的更新版本。 如果問題持續發生，請連絡應用程式廠商。

**適用於程式設計人員的資訊**

程式執行記憶體管理作業時，發生未預期的錯誤。

如果程式不小心變更執行階段堆積資料，通常就會發生此錯誤。 不過，它也會造成執行階段或作業系統的程式碼中發生內部錯誤。

若要修正此問題，請檢查程式碼中的堆積損毀錯誤。 如需詳細資訊和範例，請參閱 < [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)。 接下來，請檢查您的應用程式部署會使用最新的可轉散發套件。 如需資訊，請參閱[Visual c + + 中的部署](../../ide/deployment-in-visual-cpp.md)。