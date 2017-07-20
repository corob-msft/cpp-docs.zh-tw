---
title: "加法 (+) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "指標, 整數相加"
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 加法 (+)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

加法運算子 \(**\+**\) 會使它的兩個運算元相加。  這兩個運算元都可以是整數類資料類型或浮點類型，或是一個運算元為指標，另一個為整數。  
  
 當整數與指標相加時，會藉由將整數值 \(*i*\) 乘以指標所定址之值的大小進行整數值轉換。  在轉換之後，整數值代表 *i* 個記憶體位置，其中每個位置的長度都是以指標類型指定。  當轉換的整數值與指標值相加時，結果會是新的指標值，表示來自原始位址的位址 *i* 位置。  新的指標值會將相同類型的值定址為原始指標值，因此與陣列索引相同 \(請參閱[一維陣列](../c-language/one-dimensional-arrays.md)和[多維陣列](../c-language/multidimensional-arrays-c.md)\)。  如果總和指標指向陣列外部，但在高位階之外的第一個位置除外，則結果會是未定義。  如需詳細資訊，請參閱[指標算術](../c-language/pointer-arithmetic.md)。  
  
## 請參閱  
 [C 加法類運算子](../c-language/c-additive-operators.md)