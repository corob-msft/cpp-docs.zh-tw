---
title: "static 儲存類別規範 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 34f60570d18882ddfb7ebef78977d6b2f5c82000
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="static-storage-class-specifier"></a>static 儲存類別規範
在內部層級使用 **static** 儲存類別指定名稱宣告的變數具有全域存留期，但是只有在宣告該變數的區塊內才看得見。 若是常數字串，使用 **static** 會很有用，因為它可減輕經常呼叫的函式中經常需要初始化的額外負荷。  
  
## <a name="remarks"></a>備註  
如果您未明確初始化 **static** 變數，該變數預設會初始化為 0。 在函式內，**static** 會配置儲存區並且做為定義。 內部靜態變數會提供只有單一函式可見的私用永久儲存區。  
  
## <a name="see-also"></a>另請參閱  
[C 儲存類別](c-storage-classes.md)  
[儲存類別 (C++)](../cpp/storage-classes-cpp.md)  