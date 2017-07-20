---
title: "CSimpleException 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException class
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5612d76a2351b9898b8ffe082844686d21fcd7a0
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="csimpleexception-class"></a>CSimpleException 類別
這個類別是資源關鍵 MFC 例外狀況的基底類別。  
  
## <a name="syntax"></a>語法  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|建構函式。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|提供有關已發生的錯誤文字。|  
  
## <a name="remarks"></a>備註  
 `CSimpleException`是資源關鍵 MFC 例外狀況的基底類別，並處理的擁有權和初始化錯誤訊息。 下列類別會使用`CSimpleException`作為其基底類別︰  
  
|||  
|-|-|  
|[Afxthrowmemoryexception 類別](../../mfc/reference/cmemoryexception-class.md)|記憶體不足例外狀況|  
|[CNotSupportedException 類別](../../mfc/reference/cnotsupportedexception-class.md)|不支援的作業的要求|  
|[CResourceException 類別](../../mfc/reference/cresourceexception-class.md)|找不到或無法建立 Windows 資源|  
|[CUserException 類別](../../mfc/reference/cuserexception-class.md)|找不到例外狀況，表示資源|  
|[CInvalidArgException 類別](../../mfc/reference/cinvalidargexception-class.md)|表示無效的引數的例外狀況|  
  
 因為`CSimpleException`是抽象的基底類別，您無法宣告`CSimpleException`直接物件。 相反地，您必須宣告衍生的物件，例如前面表格中。 如果您宣告衍生的類別，做為模型的上一個類別。  
  
 如需詳細資訊，請參閱[CException 類別](../../mfc/reference/cexception-class.md)主題和[例外狀況處理 (MFC)](../../mfc/exception-handling-in-mfc.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>需求  
 **標頭：** afx.h  
  
##  <a name="csimpleexception"></a>CSimpleException::CSimpleException  
 建構函式。  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>參數  
 `bAutoDelete`  
 指定**TRUE**如果的記憶體`CSimpleException`已在堆積上配置物件。 這將導致`CSimpleException`時刪除物件**刪除**呼叫成員函式會刪除例外狀況。 指定**FALSE**如果`CSimpleException`物件在堆疊上，或全域物件。 在此情況下，`CSimpleException`物件不會刪除**刪除**成員函式呼叫。  
  
### <a name="remarks"></a>備註  
 您通常不需要直接呼叫這個建構函式。 擲回例外狀況的函式應該建立的執行個體`CException`-衍生類別，並呼叫其建構函式，或它應該 MFC 使用其中一個擲回函式，例如[AfxThrowFileException](exception-processing.md#afxthrowfileexception)、 預先定義的型別會擲回。  
  
##  <a name="geterrormessage"></a>CSimpleException::GetErrorMessage  
 呼叫此成員函式，以提供有關已發生的錯誤文字。  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>參數  
 `lpszError`  
 將會收到錯誤訊息緩衝區的指標。  
  
 `nMaxError`  
 最大的緩衝區可以保存包括的字元數**NULL**結束字元。  
  
 `pnHelpContext`  
 位址**UINT** ，將會收到說明內容識別碼。 如果**NULL**，將會傳回任何識別碼。  
  
### <a name="return-value"></a>傳回值  
 如果函式成功則為非零否則為 0，如果沒有任何錯誤訊息文字使用。  
  
### <a name="remarks"></a>備註  
 如需詳細資訊，請參閱[CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)。  
  
## <a name="see-also"></a>另請參閱  
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [CException 類別](../../mfc/reference/cexception-class.md)   
 [例外狀況處理](../../mfc/exception-handling-in-mfc.md)



