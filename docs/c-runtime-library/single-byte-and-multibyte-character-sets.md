---
title: "單一位元組和多位元組字元集 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.character.multibyte
dev_langs:
- C++
helpviewer_keywords:
- SBCS (single byte character set)
- MBCS [C++], about MBCS
- character sets [C++], multibyte
- character sets [C++], single byte
ms.assetid: 2cbc78ea-33c0-4cfb-b0df-7ce2458431ce
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: c7d9a62c2b6dc69f9fcd86c8f498e42ce31cae84
ms.contentlocale: zh-tw
ms.lasthandoff: 04/01/2017

---
# <a name="single-byte-and-multibyte-character-sets"></a>單位元組和多位元組字元集
ASCII 字元集定義 0x00 - 0x7F 範圍內的字元。 有數個其他字元集 (主要是歐洲) 定義 0x00 - 0x7F 範圍內與 ASCII 字元集相同的字元，其也會定義 0x80 - 0xFF 的擴充字元集。 因此，8 位元單一位元組字元集 (`SBCS`) 就足以代表 ASCII 字元集，以及許多歐洲語言的字元集。 不過，有些非歐洲字元集 (例如日文漢字) 所含的字元數多於可用單一位元組編碼配置表示的字元數，因此需要多位元組字元集 (`MBCS`) 編碼。  
  
> [!NOTE]
>  Microsoft 執行階段程式庫中的許多 `SBCS` 常式都會適當地處理多位元組、字元和字串。 許多多位元組字元集都會將 ASCII 字元集定義為子集。 在許多多位元組字元集中，0x00 - 0x7F 範圍中的每個字元都會與 ASCII 字元集中具有相同值的字元相同。 例如，在 `ASCII` 和 `MBCS` 字元字串中，單位元組 `NULL` 字元 ('\0') 會有值 0x00，並指出終止的 null 字元。  
  
 多位元組字元集可能包含單位元組和雙位元組字元。 因此，多位元組字元字串可能混合單一位元組和雙位元組字元。 雙位元組多位元組字元會有一個前導位元組和一個後隨位元組。 在特定多位元組字元集中，前導位元組落在特定範圍內，後隨位元組也是如此。 這些範圍重疊時，可能需要評估特定內容，以決定指定的位元組是否作為前導位元組或後隨位元組。  
  
## <a name="see-also"></a>另請參閱  
 [國際化](../c-runtime-library/internationalization.md)   
 [依類別區分的執行階段常式](../c-runtime-library/run-time-routines-by-category.md)