---
title: "CUserToolsManager 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CUserToolsManager
- AFXUSERTOOLSMANAGER/CUserToolsManager::CreateNewTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::FindTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetArgumentsMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetFilter
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetInitialDirMenuID
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetMaxTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetToolsEntryCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::GetUserTools
- AFXUSERTOOLSMANAGER/CUserToolsManager::InvokeTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::IsUserToolCmd
- AFXUSERTOOLSMANAGER/CUserToolsManager::LoadState
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolDown
- AFXUSERTOOLSMANAGER/CUserToolsManager::MoveToolUp
- AFXUSERTOOLSMANAGER/CUserToolsManager::RemoveTool
- AFXUSERTOOLSMANAGER/CUserToolsManager::SaveState
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetDefExt
- AFXUSERTOOLSMANAGER/CUserToolsManager::SetFilter
dev_langs:
- C++
helpviewer_keywords:
- CUserToolsManager class
ms.assetid: bdfa37ae-efca-4616-abb5-9d0dcd2d335b
caps.latest.revision: 26
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
ms.openlocfilehash: 0b82adf0f9eba5ee334ada2c169546f27894c1dd
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cusertoolsmanager-class"></a>CUserToolsManager 類別
會維護的集合[CUserTool 類別](../../mfc/reference/cusertool-class.md)應用程式中的物件。 使用者工具是執行外部應用程式的功能表項目。 `CUserToolsManager` 物件可讓使用者或開發人員將新的使用者工具加入至應用程式。 它支援執行與使用者工具相關聯的命令，也會在 Windows 登錄中儲存使用者工具的相關資訊。  
  
## <a name="syntax"></a>語法  
  
```  
class CUserToolsManager : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CUserToolsManager::CUserToolsManager](#cusertoolsmanager)|建構 `CUserToolsManager`。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[CUserToolsManager::CreateNewTool](#createnewtool)|建立新的使用者工具。|  
|[CUserToolsManager::FindTool](#findtool)|傳回的指標`CMFCUserTool`與指定的命令識別碼相關聯的物件|  
|[CUserToolsManager::GetArgumentsMenuID](#getargumentsmenuid)|傳回相關聯的資源識別碼**引數**功能表**工具** 索引標籤的**自訂**對話方塊。|  
|[CUserToolsManager::GetDefExt](#getdefext)|傳回預設的延伸模組**開啟舊檔**對話方塊 ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。|  
|[CUserToolsManager::GetFilter](#getfilter)|傳回檔案篩選器**開啟舊檔**對話方塊 ( [CFileDialog 類別](../../mfc/reference/cfiledialog-class.md)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。|  
|[CUserToolsManager::GetInitialDirMenuID](#getinitialdirmenuid)|傳回相關聯的資源識別碼**初始目錄**功能表**工具** 索引標籤的**自訂**對話方塊。|  
|[CUserToolsManager::GetMaxTools](#getmaxtools)|傳回應用程式的使用者工具，可配置的數目上限。|  
|[CUserToolsManager::GetToolsEntryCmd](#gettoolsentrycmd)|傳回使用者工具的功能表項目預留位置的命令 ID。|  
|[CUserToolsManager::GetUserTools](#getusertools)|傳回使用者工具清單的參考。|  
|[CUserToolsManager::InvokeTool](#invoketool)|執行應用程式相關聯的使用者工具有指定的命令識別碼。|  
|[CUserToolsManager::IsUserToolCmd](#isusertoolcmd)|判斷是否與使用者工具相關聯的命令識別碼。|  
|[CUserToolsManager::LoadState](#loadstate)|從 Windows 登錄載入使用者工具的相關資訊。|  
|[CUserToolsManager::MoveToolDown](#movetooldown)|使用者工具清單中，向下移動指定的使用者工具。|  
|[CUserToolsManager::MoveToolUp](#movetoolup)|在使用者工具清單中，向上移動指定的使用者工具。|  
|[CUserToolsManager::RemoveTool](#removetool)|從應用程式中移除指定的使用者工具。|  
|[CUserToolsManager::SaveState](#savestate)|在 Windows 登錄中儲存使用者工具的相關資訊。|  
|[CUserToolsManager::SetDefExt](#setdefext)|指定預設的延伸模組，**開啟舊檔**對話方塊 ( [CFileDialog 類別](../../mfc/reference/cfiledialog-class.md)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。|  
|[CUserToolsManager::SetFilter](#setfilter)|指定檔案篩選器，**開啟舊檔**對話方塊 ( [CFileDialog 類別](../../mfc/reference/cfiledialog-class.md)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。|  
  
## <a name="remarks"></a>備註  
 若要併入您的應用程式的使用者工具，您必須︰  
  
 1. 保留的功能表項目相關聯的命令 ID 的使用者工具 功能表項目。  
  
 2. 保留每個使用者可以在您的應用程式中定義的使用者工具循序命令 ID。  
  
 3. 呼叫[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)方法，並提供下列參數︰ 功能表命令 ID、 第一個使用者工具命令 ID，以及最後一個使用者工具的命令 id。  
  
 應該只有一個全域`CUserToolsManager`每個應用程式的物件。  
  
 如需使用者工具的範例，請參閱 VisualStudioDemo 範例專案。  
  
## <a name="example"></a>範例  
 下列範例示範如何擷取參考`CUserToolsManager`物件，以及如何建立新的使用者工具。 此程式碼片段是一部分[Visual Studio 示範範例](../../visual-cpp-samples.md)。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&38;](../../mfc/codesnippet/cpp/cusertoolsmanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUserToolsManager`  
  
## <a name="requirements"></a>需求  
 **標頭︰** afxusertoolsmanager.h  
  
##  <a name="createnewtool"></a>CUserToolsManager::CreateNewTool  
 建立新的使用者工具。  
  
```  
CUserTool* CreateNewTool();
```  
  
### <a name="return-value"></a>傳回值  
 新建立的使用者工具的指標或`NULL`如果使用者工具數目已超過最大值。 傳回的型別是型別傳遞至相同`CWinAppEx::EnableUserTools`為`pToolRTC`參數。  
  
### <a name="remarks"></a>備註  
 此方法的呼叫中提供的範圍中找到的第一個可用的功能表命令 ID [CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools) ，並指派使用者工具，此識別碼。  
  
 如果工具數目已達到最大值，方法就會失敗。 這發生在範圍內的所有命令 Id 都指派給使用者工具。 您可以擷取之工具的最大數目，藉由呼叫[CUserToolsManager::GetMaxTools](#getmaxtools)。 您可以呼叫來取得存取權的工具清單[CUserToolsManager::GetUserTools](#getusertools)方法。  
  
##  <a name="cusertoolsmanager"></a>CUserToolsManager::CUserToolsManager  
 建構 `CUserToolsManager`。 每個應用程式必須有最多一位使用者工具管理員。  
  
```  
CUserToolsManager();

 
CUserToolsManager(
    const UINT uiCmdToolsDummy,  
    const UINT uiCmdFirst,  
    const UINT uiCmdLast,  
    CRuntimeClass* pToolRTC=RUNTIME_CLASS(CUserTool),  
    UINT uArgMenuID=0,  
    UINT uInitDirMenuID=0);
```  
  
### <a name="parameters"></a>參數  
 [in] `uiCmdToolsDummy`  
 不帶正負號的整數，架構會使用預留位置做為使用者的 [工具] 功能表的命令 ID。  
  
 [in] `uiCmdFirst`  
 第一次的使用者工具命令的命令 ID。  
  
 [in] `uiCmdLast`  
 最後的使用者工具命令的命令 ID。  
  
 [in] `pToolRTC`  
 此類別的[CUserToolsManager::CreateNewTool](#createnewtool)建立。 藉由使用這個類別，您可以使用衍生的型別[CUserTool 類別](../../mfc/reference/cusertool-class.md)而不是預設的實作。  
  
 [in] `uArgMenuID`  
 引數快顯功能表的功能表資源識別碼。  
  
 [in] `uInitDirMenuID`  
 初始目錄的快顯功能表的功能表資源識別碼。  
  
### <a name="remarks"></a>備註  
 請勿呼叫這個建構函式。 請改為呼叫[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)啟用使用者工具，並呼叫[CWinAppEx::GetUserToolsManager](../../mfc/reference/cwinappex-class.md#getusertoolsmanager)取得指標`CUserToolsManager`。 如需詳細資訊，請參閱[使用者定義工具](../../mfc/user-defined-tools.md)。  
  
##  <a name="findtool"></a>CUserToolsManager::FindTool  
 傳回的指標[CUserTool 類別](../../mfc/reference/cusertool-class.md)與指定的命令識別碼相關聯的物件  
  
```  
CUserTool* FindTool(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `uiCmdId`  
 功能表命令的識別項。  
  
### <a name="return-value"></a>傳回值  
 指標[CUserTool 類別](../../mfc/reference/cusertool-class.md)或`CUserTool`-衍生物件，如果成功，否則為`NULL`。  
  
### <a name="remarks"></a>備註  
 當`FindTool`會成功，傳回的型別是相同的型別`pToolRTC`參數[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)。  
  
##  <a name="getargumentsmenuid"></a>CUserToolsManager::GetArgumentsMenuID  
 傳回相關聯的資源識別碼**引數**功能表**工具** 索引標籤的**自訂**對話方塊。  
  
```  
UINT GetArgumentsMenuID() const;  
```  
  
### <a name="return-value"></a>傳回值  
 功能表資源的識別項。  
  
### <a name="remarks"></a>備註  
 `uArgMenuID`參數[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)指定的資源識別碼。  
  
##  <a name="getdefext"></a>CUserToolsManager::GetDefExt  
 傳回預設的延伸模組**開啟舊檔**對話方塊 ( [CFileDialog](../../mfc/reference/cfiledialog-class.md#cfiledialog)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。  
  
```  
const CString& GetDefExt() const;  
```  
  
### <a name="return-value"></a>傳回值  
 參考`CString`包含延伸的物件。  
  
##  <a name="getfilter"></a>CUserToolsManager::GetFilter  
 傳回檔案篩選器**開啟舊檔**對話方塊 ( [CFileDialog 類別](../../mfc/reference/cfiledialog-class.md)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。  
  
```  
const CString& GetFilter() const;  
```  
  
### <a name="return-value"></a>傳回值  
 參考`CString`包含篩選條件的物件。  
  
##  <a name="getinitialdirmenuid"></a>CUserToolsManager::GetInitialDirMenuID  
 傳回相關聯的資源識別碼**初始目錄**功能表**工具** 索引標籤的**自訂**對話方塊。  
  
```  
UINT GetInitialDirMenuID() const;  
```  
  
### <a name="return-value"></a>傳回值  
 功能表資源的識別項。  
  
### <a name="remarks"></a>備註  
 傳回的識別碼中指定`uInitDirMenuID`參數[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)。  
  
##  <a name="getmaxtools"></a>CUserToolsManager::GetMaxTools  
 傳回應用程式的使用者工具，可配置的數目上限。  
  
```  
int GetMaxTools() const;  
```  
  
### <a name="return-value"></a>傳回值  
 可配置的使用者工具的數目上限。  
  
### <a name="remarks"></a>備註  
 呼叫此方法以擷取工具，可配置在應用程式的最大數目。 這個數字是從範圍中的識別碼數目`uiCmdFirst`透過`uiCmdLast`參數傳遞至[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)。  
  
##  <a name="gettoolsentrycmd"></a>CUserToolsManager::GetToolsEntryCmd  
 傳回使用者工具的功能表項目預留位置的命令 ID。  
  
```  
UINT GetToolsEntryCmd() const;  
```  
  
### <a name="return-value"></a>傳回值  
 預留位置的命令 ID。  
  
### <a name="remarks"></a>備註  
 若要啟用使用者工具，請呼叫[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)。 `uiCmdToolsDummy`參數會指定工具的 [項目] 命令的命令 ID。 這個方法會傳回工具項目的命令 id。 只要使用該識別碼，就在功能表中，它會取代使用者工具的清單時，功能表隨即出現。  
  
##  <a name="getusertools"></a>CUserToolsManager::GetUserTools  
 傳回使用者工具清單的參考。  
  
```  
const CObList& GetUserTools() const;  
```  
  
### <a name="return-value"></a>傳回值  
 常數參考的[CObList 類別](../../mfc/reference/coblist-class.md)物件，其中包含一份使用者工具。  
  
### <a name="remarks"></a>備註  
 呼叫這個方法，以擷取一份使用者工具[CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)物件會維護。 每個使用者工具由型別的物件[CUserTool 類別](../../mfc/reference/cusertool-class.md)或型別衍生自`CUserTool`。 型別由指定`pToolRTC`參數，當您呼叫[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)來讓使用者工具。  
  
##  <a name="invoketool"></a>CUserToolsManager::InvokeTool  
 執行應用程式相關聯的使用者工具有指定的命令識別碼。  
  
```  
BOOL InvokeTool(UINT uiCmdId);
```  
  
### <a name="parameters"></a>參數  
 [in] `uiCmdId`  
 功能表命令識別碼與使用者工具相關聯。  
  
### <a name="return-value"></a>傳回值  
 如果與使用者工具相關聯的命令執行成功則為非零否則為 0。  
  
### <a name="remarks"></a>備註  
 呼叫此方法以執行與使用者相關聯的應用程式工具，具有所指定的命令 ID `uiCmdId`。  
  
##  <a name="isusertoolcmd"></a>CUserToolsManager::IsUserToolCmd  
 判斷是否與使用者工具相關聯的命令識別碼。  
  
```  
BOOL IsUserToolCmd(UINT uiCmdId) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `uiCmdId`  
 功能表項目的命令 ID。  
  
### <a name="return-value"></a>傳回值  
 指定的命令 ID 相關聯的使用者工具; 如果為非零否則為 0。  
  
### <a name="remarks"></a>備註  
 這個方法會檢查是否指定的命令 ID 的命令識別碼範圍中。 您指定的範圍，當您呼叫[CWinAppEx::EnableUserTools](../../mfc/reference/cwinappex-class.md#enableusertools)來讓使用者工具。  
  
##  <a name="loadstate"></a>CUserToolsManager::LoadState  
 從 Windows 登錄載入使用者工具的相關資訊。  
  
```  
BOOL LoadState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>參數  
 [in] `lpszProfileName`  
 Windows 登錄機碼的路徑。  
  
### <a name="return-value"></a>傳回值  
 如果已成功; 載入狀態為非零否則為 0。  
  
### <a name="remarks"></a>備註  
 這個方法會載入的狀態`CUserToolsManager`從 Windows 登錄的物件。  
  
 通常，您無法進行直接呼叫這個方法。 [CWinAppEx::LoadState](../../mfc/reference/cwinappex-class.md#loadstate)呼叫做為工作區初始化程序的一部分。  
  
##  <a name="movetooldown"></a>CUserToolsManager::MoveToolDown  
 使用者工具清單中，向下移動指定的使用者工具。  
  
```  
BOOL MoveToolDown(CUserTool* pTool);
```  
  
### <a name="parameters"></a>參數  
 [in] `pTool`  
 指定要移動的使用者工具。  
  
### <a name="return-value"></a>傳回值  
 如果使用者工具已順利啟動。 移往下，非零值。否則為 0。  
  
### <a name="remarks"></a>備註  
 方法失敗，如果此工具，`pTool`指定不是內部的清單，否則此工具會在清單中最後一個。  
  
##  <a name="movetoolup"></a>CUserToolsManager::MoveToolUp  
 在使用者工具清單中，向上移動指定的使用者工具。  
  
```  
BOOL MoveToolUp(CUserTool* pTool);
```  
  
### <a name="parameters"></a>參數  
 [in] `pTool`  
 指定要移動的使用者工具。  
  
### <a name="return-value"></a>傳回值  
 如果使用者工具已順利啟動。 移，非零值。否則為 0。  
  
### <a name="remarks"></a>備註  
 方法會失敗，如果工具的`pTool`參數會指定不在內部清單或此工具是否在清單中的第一個工具項目。  
  
##  <a name="removetool"></a>CUserToolsManager::RemoveTool  
 從應用程式中移除指定的使用者工具。  
  
```  
BOOL RemoveTool(CUserTool* pTool);
```  
  
### <a name="parameters"></a>參數  
 [in、out] `pTool`  
 要移除的使用者工具指標。  
  
### <a name="return-value"></a>傳回值  
 `TRUE`如果成功移除工具。 否則為 `FALSE`。  
  
### <a name="remarks"></a>備註  
 如果成功移除工具，則這個方法會刪除`pTool`。  
  
##  <a name="savestate"></a>CUserToolsManager::SaveState  
 在 Windows 登錄中儲存使用者工具的相關資訊。  
  
```  
BOOL SaveState(LPCTSTR lpszProfileName=NULL);
```  
  
### <a name="parameters"></a>參數  
 [in] `lpszProfileName`  
 Windows 登錄機碼路徑。  
  
### <a name="return-value"></a>傳回值  
 如果成功，已儲存的狀態為非零否則為 0。  
  
### <a name="remarks"></a>備註  
 方法會儲存目前的狀態`CUserToolsManager`Windows 登錄中的物件。  
  
 通常您不需要直接呼叫這個方法[CWinAppEx::SaveState](../../mfc/reference/cwinappex-class.md#savestate)應用程式的工作區序列化程序的一部分自動呼叫它。  
  
##  <a name="setdefext"></a>CUserToolsManager::SetDefExt  
 指定預設的延伸模組，**開啟舊檔**對話方塊 ( [CFileDialog 類別](../../mfc/reference/cfiledialog-class.md)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。  
  
```  
void SetDefExt(const CString& strDefExt);
```  
  
### <a name="parameters"></a>參數  
 [in] `strDefExt`  
 文字字串，其中包含預設的副檔名。  
  
### <a name="remarks"></a>備註  
 呼叫這個方法來指定預設檔案名稱副檔名中的**開啟舊檔**對話方塊中，將會顯示當使用者選取要與使用者工具產生關聯的應用程式。 預設為"exe"。  
  
##  <a name="setfilter"></a>CUserToolsManager::SetFilter  
 指定檔案篩選器，**開啟舊檔**對話方塊 ( [CFileDialog 類別](../../mfc/reference/cfiledialog-class.md)) 中使用**命令**欄位**工具** 索引標籤的**自訂**對話方塊。  
  
```  
void SetFilter(const CString& strFilter);
```  
  
### <a name="parameters"></a>參數  
 [in] `strFilter`  
 指定的篩選器。  
  
## <a name="see-also"></a>另請參閱  
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [類別](../../mfc/reference/mfc-classes.md)   
 [Cwinappex 衍生類別](../../mfc/reference/cwinappex-class.md)   
 [CUserTool 類別](../../mfc/reference/cusertool-class.md)
