---
title: 推斷規則
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- NMAKE program, inference rules
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
ms.openlocfilehash: cb67fc8fe8e65814c9b169f7936c7d225d26e1e3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471041"
---
# <a name="inference-rules"></a>推斷規則

推斷規則提供命令，更新目標，並推斷目標的相依性。 推斷規則中的延伸模組比對單一目標，且具有相同的基底名稱的相依。 推斷規則是使用者定義或預先定義的;預先定義的規則可以重新定義。

如果過時的相依性沒有任何命令，而且如果[。後置詞](../build/dot-directives.md)包含相依的延伸模組，其副檔名符合目標和現有的規則檔案的目前或指定的目錄中的 NMAKE 使用。 如果多個規則符合現有檔案， **。後置詞**清單決定要使用哪些; 左到右向下延伸清單的優先順序。 如果相依檔案不存在，而且不是另一個描述區塊中的目標，推斷規則可以遺失相依從建立具有相同的基底名稱的另一個檔案。 如果描述區塊的目標有任何相依項目或命令，推斷規則可以更新目標。 推斷規則可以建置命令列目標，即使描述區塊不存在。 NMAKE 可能叫用的推斷相依的規則，即使未指定明確的相依性。

## <a name="what-do-you-want-to-know-more-about"></a>您還想知道關於哪些方面的詳細資訊？

[定義規則](../build/defining-a-rule.md)

[批次模式規則](../build/batch-mode-rules.md)

[預先定義的規則](../build/predefined-rules.md)

[推斷的相依和規則](../build/inferred-dependents-and-rules.md)

[推斷規則的優先順序](../build/precedence-in-inference-rules.md)

## <a name="see-also"></a>另請參閱

[NMAKE 參考](../build/nmake-reference.md)