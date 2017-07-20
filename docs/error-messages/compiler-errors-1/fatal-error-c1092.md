---
title: "嚴重錯誤 C1092 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 6d93fd662b638126e21d5f5f034138c0e6f0e0ad
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="fatal-error-c1092"></a>嚴重錯誤 C1092
編輯後繼續不支援對資料類型的變更; 需要先進行建置  
  
 變更或新增的最後一個成功組建後的資料型別。  
  
-   編輯後繼續 不支援變更現有的資料類型，包括類別、 結構或列舉的定義。 您必須停止偵錯，並建置應用程式。  
  
-   編輯後繼續 不支援附加新資料型別如果程式資料庫檔案，例如 vc*x*0.pdb (其中*x*是使用中的主要版本的 Visual c + +) 是唯讀的。 若要加入資料型別，編譯器必須在寫入模式中開啟的.pdb 檔。  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>若要移除此錯誤，而不需要結束目前的偵錯工作階段  
  
1.  請將資料類型改回錯誤之前的狀態。  
  
2.  從 [偵錯]  功能表選擇 [套用程式碼變更] 。  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>移除這個錯誤，而不變更您的原始程式碼  
  
1.  從 [偵錯]  功能表選擇 [停止偵錯] 。  
  
2.  從 [建置]  功能表選擇 [建置] 。  
  
 如需詳細資訊，請參閱[支援的程式碼變更](/visualstudio/debugger/supported-code-changes-cpp)。