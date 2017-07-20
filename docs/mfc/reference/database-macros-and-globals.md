---
title: "資料庫巨集和全域 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs:
- C++
helpviewer_keywords:
- global database functions [C++]
- database macros [C++]
- database globals [C++]
- global functions [C++], database functions
- macros [C++], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: 13
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
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: ddf13f6458df387d6686a18ecd459938ef2ebafd
ms.contentlocale: zh-tw
ms.lasthandoff: 04/04/2017

---
# <a name="database-macros-and-globals"></a>資料庫巨集和全域
以下所列的巨集和全域資料適用於採用 ODBC 的資料庫應用程式。 它們不適用於採用 DAO 的應用程式。  
  
 在 MFC 4.2 之前，巨集 `AFX_SQL_ASYNC` 和 `AFX_SQL_SYNC` 為非同步作業提供一個產生時間給其他處理序的機會。 從 MFC 4.2 開始，因為 MFC ODBC 類別只使用同步作業，因此已變更這些巨集的實作。 巨集 `AFX_ODBC_CALL` 是 MFC 4.2 的新增功能。  
  
### <a name="database-macros"></a>資料庫巨集  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|呼叫傳回 `SQL_STILL_EXECUTING` 的 ODBC API 函式。 `AFX_ODBC_CALL` 將會重複呼叫函式，直到它不再傳回 `SQL_STILL_EXECUTING`。|  
|[AFX_SQL_ASYNC](#afx_sql_async)|呼叫 `AFX_ODBC_CALL`。|  
|[AFX_SQL_SYNC](#afx_sql_sync)|呼叫不傳回 `SQL_STILL_EXECUTING` 的 ODBC API 函式。|  
  
### <a name="database-globals"></a>資料庫全域  
  
|||  
|-|-| 
|[AfxDbInitModule](#afxdbinitmodule)|加入動態連結至 MFC 之標準 DLL 的資料庫支援。| 
|[AfxGetHENV](#afxgethenv)|擷取目前正在由 MFC 使用的 ODBC 環境控制代碼。 您可以直接呼叫 ODBC 時使用這個控制代碼。|  


## <a name="afxdbinitmodule"></a>AfxDbInitModule
MFC 資料庫 （或 DAO） 支援從動態連結至 MFC 之標準 DLL，加入這個函式呼叫中標準 DLL 的**Afxenablecontrolcontainer**函式來初始化 MFC 資料庫 DLL。  
   
### <a name="syntax"></a>語法    
```
void AFXAPI AfxDbInitModule( );    
```  
   
### <a name="remarks"></a>備註  
 請確定這個呼叫發生之前的任何基底類別呼叫或任何加入的程式碼會存取 MFC 資料庫 DLL。 MFC 資料庫 DLL 是一個擴充 DLL;為了讓擴充 DLL 至**CDynLinkLibrary**鏈結，就必須建立**CDynLinkLibrary**將會使用每個模組的內容中的物件。 `AfxDbInitModule`建立**CDynLinkLibrary**標準 DLL 的內容中的物件，讓它取得**CDynLinkLibrary**物件的標準 DLL 的鏈結。  
   
### <a name="requirements"></a>需求  
 **標頭︰**<afxdll_.h></afxdll_.h>  
   
### <a name="see-also"></a>另請參閱  
 [巨集和全域變數](mfc-macros-and-globals.md)
 
  

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL  
 使用這個巨集呼叫可能會傳回任何 ODBC API 函式`SQL_STILL_EXECUTING`。  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>參數  
 `SQLFunc`  
 ODBC API 函式。 如需 ODBC API 函式的詳細資訊，請參閱 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="remarks"></a>備註  
 `AFX_ODBC_CALL`重複呼叫函式直到它不再傳回`SQL_STILL_EXECUTING`。  
  
 叫用之前`AFX_ODBC_CALL`，您必須宣告一個變數， `nRetCode`，型別**RETCODE**。  
  
 請注意 MFC ODBC 類別現在使用只同步處理。 為了執行非同步作業，您必須呼叫 ODBC API 函式**SQLSetConnectOption**。 如需詳細資訊，請參閱 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 中的「非同步執行函式」主題。  

  
### <a name="example"></a>範例  
 這個範例會使用`AFX_ODBC_CALL`呼叫**SQLColumns** ODBC API 函式，它會傳回名為資料表中的資料行清單`strTableName`。 請注意的宣告`nRetCode`以及將參數傳遞給函式的資料錄集的資料成員使用。 此範例也說明檢查與呼叫的結果**檢查**，類別的成員函式`CRecordset`。 變數`prs`是指向`CRecordset`宣告其他位置的物件。  
  
 [!code-cpp[NVC_MFCDatabase # 39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>需求  
 **標頭︰** afxdb.h  

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC  
 在 MFC 4.2 變更這個巨集實作。  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>參數  
 `prs`  
 `CRecordset` 物件或 `CDatabase` 物件指標。 從 MFC 4.2 開始略過這個參數值。  
  
 `SQLFunc`  
 ODBC API 函式。 如需 ODBC API 函式的詳細資訊，請參閱 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="remarks"></a>備註  
 `AFX_SQL_ASYNC`只會呼叫巨集[AFX_ODBC_CALL](#afx_odbc_call)並忽略`prs`參數。 在 MFC 4.2 之前的版本中，`AFX_SQL_ASYNC` 是用來呼叫可能傳回 `SQL_STILL_EXECUTING` 的 ODBC API 函式。 如果 ODBC API 函式確實傳回 `SQL_STILL_EXECUTING`，則 `AFX_SQL_ASYNC` 會呼叫 `prs->OnWaitForDataSource`。  
  
> [!NOTE]
>  MFC ODBC 類別現在只會使用同步處理。 為了執行非同步作業，您必須呼叫 ODBC API 函式**SQLSetConnectOption**。 如需詳細資訊，請參閱 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 中的「非同步執行函式」主題。  
  
### <a name="requirements"></a>需求  
  **標頭**afxdb.h  
  
##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC  
 `AFX_SQL_SYNC`巨集只會呼叫此函式`SQLFunc`。  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>參數  
 `SQLFunc`  
 ODBC API 函式。 如需有關這些函式的詳細資訊，請參閱[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="remarks"></a>備註  
 使用這個巨集呼叫 ODBC API 函式，將不會傳回`SQL_STILL_EXECUTING`。  
  
 然後再呼叫`AFX_SQL_SYNC`，您必須宣告一個變數， `nRetCode`，型別**RETCODE**。 您可以檢查的值`nRetCode`巨集呼叫之後。  
  
 請注意，實作`AFX_SQL_SYNC`在 MFC 4.2 變更。 檢查伺服器的狀態已不再需要，因為`AFX_SQL_SYNC`只指派將值`nRetCode`。 例如，而不是進行呼叫  
  
 [!code-cpp[NVC_MFCDatabase # 40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 您可以只進行指派  
  
 [!code-cpp[NVC_MFCDatabase # 41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>需求  
  **標頭**afxdb.h  
  
##  <a name="afxgethenv"></a>AfxGetHENV  
 您可以直接呼叫 ODBC 使用傳回的控制代碼，但是必須不關閉此控制代碼或假設控制代碼仍然有效且可用之後任何現有`CDatabase`-或`CRecordset`-衍生的物件已被終結。  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>傳回值  
 目前正在由 MFC 使用的 ODBC 環境控制代碼。 可以是`SQL_HENV_NULL`是否有任何[CDatabase](../../mfc/reference/cdatabase-class.md)物件，且沒有[CRecordset](../../mfc/reference/crecordset-class.md)中使用的物件。  
  
### <a name="requirements"></a>需求  
  **標頭**afxdb.h  
    
## <a name="see-also"></a>另請參閱  
 [巨集和全域變數](../../mfc/reference/mfc-macros-and-globals.md)
