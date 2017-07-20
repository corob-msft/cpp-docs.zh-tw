---
title: "範例容器成員 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- container classes
ms.assetid: dc5a1998-a31b-4adf-b888-8abe5b87a4e0
caps.latest.revision: 9
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 2d8485f7fa62f2aaf3d3e6be920620aaf14fd7ca
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="sample-container-members"></a>範例容器成員
> [!NOTE]
>  本主題位於 Visual C++ 文件內，可做為 C++ 標準程式庫中所用容器的無作用範例。 如需詳細資訊，請參閱 [C++ 標準程式庫容器](../standard-library/stl-containers.md)。  
  
## <a name="reference"></a>參考資料  
  
## <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[const_iterator](../standard-library/container-class-const-iterator.md)|描述的物件可作為受控制序列的常數迭代器。|  
|[const_reference](../standard-library/container-class-const-reference.md)|描述的物件可作為受控制序列之項目的常數參考。|  
|[const_reverse_iterator](../standard-library/container-class-const-reverse-iterator.md)|描述的物件可作為受控制序列的常數反向迭代器。|  
|[difference_type](../standard-library/container-class-difference-type.md)|描述的物件可代表受控制序列中任兩個項目位址之間的差距。|  
|[iterator](../standard-library/container-class-iterator.md)|描述的物件可作為受控制序列的迭代器。|  
|[reference](../standard-library/container-class-reference.md)|描述的物件可作為受控制序列的項目參考。|  
|[reverse_iterator](../standard-library/container-class-reverse-iterator.md)|描述的物件可作為受控制序列的反向迭代器。|  
|[size_type](../standard-library/container-class-size-type.md)|描述的物件可代表任何受控制序列的長度。|  
|[value_type](../standard-library/container-class-value-type.md)|作為 **Ty** 樣板參數的同義字。|  
  
## <a name="member-functions"></a>成員函式  
  
|||  
|-|-|  
|[begin](../standard-library/container-class-begin.md)|傳回迭代器，指向序列的第一個項目 (或空序列結尾以外的位置)。|  
|[clear](../standard-library/container-class-clear.md)|呼叫 [erase](../standard-library/container-class-erase.md)( [begin](../standard-library/container-class-begin.md), [end](../standard-library/container-class-end.md))。|  
|[empty](../standard-library/container-class-empty.md)|對空的受控制序列傳回 **true**。|  
|[end](../standard-library/container-class-end.md)|傳回指向序列結尾之外的迭代器。|  
|[erase](../standard-library/container-class-erase.md)|清除項目。|  
|[max_size](../standard-library/container-class-max-size.md)|傳回物件可控制的最長序列長度 (不論受控制序列的長度為何，且為定時的狀態)。|  
|[rbegin](../standard-library/container-class-rbegin.md)|傳回指向受控制序列結尾之外的反向迭代器，並指定反向序列的開頭。|  
|[rend](../standard-library/container-class-rend.md)|成員函式會傳回反向迭代器，指向序列的第一個項目 (或空序列結尾以外的位置)，並指定反向序列的結尾。|  
|[size](../standard-library/container-class-size.md)|傳回受控制序列的長度 (不論受控制序列的長度為何，且為定時的狀態)。|  
|[swap](../standard-library/container-class-swap.md)
