---
title: "CTaskDialog 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTaskDialog
- AFXTASKDIALOG/CTaskDialog
- AFXTASKDIALOG/CTaskDialog::CTaskDialog
- AFXTASKDIALOG/CTaskDialog::AddCommandControl
- AFXTASKDIALOG/CTaskDialog::AddRadioButton
- AFXTASKDIALOG/CTaskDialog::ClickCommandControl
- AFXTASKDIALOG/CTaskDialog::ClickRadioButton
- AFXTASKDIALOG/CTaskDialog::DoModal
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonCount
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonFlag
- AFXTASKDIALOG/CTaskDialog::GetCommonButtonId
- AFXTASKDIALOG/CTaskDialog::GetOptions
- AFXTASKDIALOG/CTaskDialog::GetSelectedCommandControlID
- AFXTASKDIALOG/CTaskDialog::GetSelectedRadioButtonID
- AFXTASKDIALOG/CTaskDialog::GetVerificationCheckboxState
- AFXTASKDIALOG/CTaskDialog::IsCommandControlEnabled
- AFXTASKDIALOG/CTaskDialog::IsRadioButtonEnabled
- AFXTASKDIALOG/CTaskDialog::IsSupported
- AFXTASKDIALOG/CTaskDialog::LoadCommandControls
- AFXTASKDIALOG/CTaskDialog::LoadRadioButtons
- AFXTASKDIALOG/CTaskDialog::NavigateTo
- AFXTASKDIALOG/CTaskDialog::OnCommandControlClick
- AFXTASKDIALOG/CTaskDialog::OnCreate
- AFXTASKDIALOG/CTaskDialog::OnDestroy
- AFXTASKDIALOG/CTaskDialog::OnExpandButtonClick
- AFXTASKDIALOG/CTaskDialog::OnHelp
- AFXTASKDIALOG/CTaskDialog::OnHyperlinkClick
- AFXTASKDIALOG/CTaskDialog::OnInit
- AFXTASKDIALOG/CTaskDialog::OnNavigatePage
- AFXTASKDIALOG/CTaskDialog::OnRadioButtonClick
- AFXTASKDIALOG/CTaskDialog::OnTimer
- AFXTASKDIALOG/CTaskDialog::OnVerificationCheckboxClick
- AFXTASKDIALOG/CTaskDialog::RemoveAllCommandControls
- AFXTASKDIALOG/CTaskDialog::RemoveAllRadioButtons
- AFXTASKDIALOG/CTaskDialog::SetCommandControlOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetCommonButtons
- AFXTASKDIALOG/CTaskDialog::SetContent
- AFXTASKDIALOG/CTaskDialog::SetDefaultCommandControl
- AFXTASKDIALOG/CTaskDialog::SetDefaultRadioButton
- AFXTASKDIALOG/CTaskDialog::SetDialogWidth
- AFXTASKDIALOG/CTaskDialog::SetExpansionArea
- AFXTASKDIALOG/CTaskDialog::SetFooterIcon
- AFXTASKDIALOG/CTaskDialog::SetFooterText
- AFXTASKDIALOG/CTaskDialog::SetMainIcon
- AFXTASKDIALOG/CTaskDialog::SetMainInstruction
- AFXTASKDIALOG/CTaskDialog::SetOptions
- AFXTASKDIALOG/CTaskDialog::SetProgressBarMarquee
- AFXTASKDIALOG/CTaskDialog::SetProgressBarPosition
- AFXTASKDIALOG/CTaskDialog::SetProgressBarRange
- AFXTASKDIALOG/CTaskDialog::SetProgressBarState
- AFXTASKDIALOG/CTaskDialog::SetRadioButtonOptions
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckbox
- AFXTASKDIALOG/CTaskDialog::SetVerificationCheckboxText
- AFXTASKDIALOG/CTaskDialog::SetWindowTitle
- AFXTASKDIALOG/CTaskDialog::ShowDialog
- AFXTASKDIALOG/CTaskDialog::TaskDialogCallback
dev_langs:
- C++
helpviewer_keywords:
- CTaskDialog class
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
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
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: d7e0335cc88fbba1a07d86b5e44e040eaad47f2f
ms.contentlocale: zh-tw
ms.lasthandoff: 04/12/2017

---
# <a name="ctaskdialog-class"></a>CTaskDialog Class
功能像訊息方塊，但是可向使用者顯示其他資訊的快顯對話方塊。 `CTaskDialog` 也包含從使用者收集資訊的功能。  
  
## <a name="syntax"></a>語法  
  
```  
class CTaskDialog : public CObject  
```  
  
## <a name="members"></a>Members  
  
### <a name="constructors"></a>建構函式  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](#ctaskdialog)|建構 `CTaskDialog` 物件。|  
  
### <a name="methods"></a>方法  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](#addcommandcontrol)|將命令按鈕控制項，以`CTaskDialog`。|  
|[CTaskDialog::AddRadioButton](#addradiobutton)|加入選項按鈕， `CTaskDialog`。|  
|[CTaskDialog::ClickCommandControl](#clickcommandcontrol)|以程式設計的方式，請按一下命令按鈕控制項或常見的按鈕。|  
|[CTaskDialog::ClickRadioButton](#clickradiobutton)|以程式設計方式按一下選項按鈕。|  
|[CTaskDialog::DoModal](#domodal)|顯示`CTaskDialog`。|  
|[CTaskDialog::GetCommonButtonCount](#getcommonbuttoncount)|擷取可用的通用按鈕數目。|  
|[CTaskDialog::GetCommonButtonFlag](#getcommonbuttonflag)|將一般的按鈕類型的 [Windows] 按鈕相關聯的標準轉換`CTaskDialog`類別。|  
|[CTaskDialog::GetCommonButtonId](#getcommonbuttonid)|將轉換其中一個常見的按鈕類型相關聯`CTaskDialog`標準 Windows 按鈕的類別。|  
|[CTaskDialog::GetOptions](#getoptions)|傳回這個選項旗標`CTaskDialog`。|  
|[CTaskDialog::GetSelectedCommandControlID](#getselectedcommandcontrolid)|傳回選取的命令按鈕控制項。|  
|[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)|傳回選取的選項按鈕。|  
|[CTaskDialog::GetVerificationCheckboxState](#getverificationcheckboxstate)|擷取驗證 核取方塊的狀態。|  
|[CTaskDialog::IsCommandControlEnabled](#iscommandcontrolenabled)|判斷是否已啟用命令按鈕控制項或常見的按鈕。|  
|[CTaskDialog::IsRadioButtonEnabled](#isradiobuttonenabled)|判斷是否已啟用的選項按鈕。|  
|[CTaskDialog::IsSupported](#issupported)|判斷是否正在執行的應用程式的電腦支援`CTaskDialog`。|  
|[CTaskDialog::LoadCommandControls](#loadcommandcontrols)|使用字串資料表中的資料，以新增命令按鈕控制項。|  
|[CTaskDialog::LoadRadioButtons](#loadradiobuttons)|使用字串資料表中的資料，以新增選項按鈕。|  
|[CTaskDialog::NavigateTo](#navigateto)|將焦點轉移到另一個`CTaskDialog`。|  
|[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)|當使用者按一下的命令按鈕控制項，架構會呼叫這個方法。|  
|[CTaskDialog::OnCreate](#oncreate)|建立之後，架構會呼叫這個方法`CTaskDialog`。|  
|[CTaskDialog::OnDestroy](#ondestroy)|架構會呼叫這個方法，它會終結之前，立即`CTaskDialog`。|  
|[CTaskDialog::OnExpandButtonClick](#onexpandbuttonclick)|當使用者按一下 [展開] 按鈕時，架構會呼叫這個方法。|  
|[CTaskDialog::OnHelp](#onhelp)|當使用者要求說明時，架構會呼叫這個方法。|  
|[CTaskDialog::OnHyperlinkClick](#onhyperlinkclick)|當使用者按一下超連結時，架構會呼叫這個方法。|  
|[CTaskDialog::OnInit](#oninit)|架構會呼叫這個方法時`CTaskDialog`已初始化。|  
|[CTaskDialog::OnNavigatePage](#onnavigatepage)|架構會呼叫這個方法，當使用者將焦點方面控制項`CTaskDialog`。|  
|[CTaskDialog::OnRadioButtonClick](#onradiobuttonclick)|當使用者選取選項按鈕控制項，架構會呼叫這個方法。|  
|[CTaskDialog::OnTimer](#ontimer)|在計時器逾時，架構會呼叫這個方法。|  
|[CTaskDialog::OnVerificationCheckboxClick](#onverificationcheckboxclick)|當使用者按一下 [驗證] 核取方塊，架構會呼叫這個方法。|  
|[CTaskDialog::RemoveAllCommandControls](#removeallcommandcontrols)|移除從所有命令控制項`CTaskDialog`。|  
|[CTaskDialog::RemoveAllRadioButtons](#removeallradiobuttons)|移除所有選項按鈕，從`CTaskDialog`。|  
|[CTaskDialog::SetCommandControlOptions](#setcommandcontroloptions)|更新命令按鈕控制項上`CTaskDialog`。|  
|[CTaskDialog::SetCommonButtonOptions](#setcommonbuttonoptions)|更新通用的按鈕，以啟用需要 UAC 提高權限的子集。|  
|[CTaskDialog::SetCommonButtons](#setcommonbuttons)|加入至一般按鈕`CTaskDialog`。|  
|[CTaskDialog::SetContent](#setcontent)|更新的內容`CTaskDialog`。|  
|[CTaskDialog::SetDefaultCommandControl](#setdefaultcommandcontrol)|指定的預設命令按鈕控制項。|  
|[CTaskDialog::SetDefaultRadioButton](#setdefaultradiobutton)|指定的預設選項按鈕。|  
|[CTaskDialog::SetDialogWidth](#setdialogwidth)|調整的寬度， `CTaskDialog`。|  
|[CTaskDialog::SetExpansionArea](#setexpansionarea)|更新的擴充區域`CTaskDialog`。|  
|[CTaskDialog::SetFooterIcon](#setfootericon)|更新的頁尾圖示`CTaskDialog`。|  
|[CTaskDialog::SetFooterText](#setfootertext)|更新上頁尾的文字`CTaskDialog`。|  
|[CTaskDialog::SetMainIcon](#setmainicon)|更新的主要圖示`CTaskDialog`。|  
|[CTaskDialog::SetMainInstruction](#setmaininstruction)|更新的主要指示`CTaskDialog`。|  
|[CTaskDialog::SetOptions](#setoptions)|會設定的選項`CTaskDialog`。|  
|[CTaskDialog::SetProgressBarMarquee](#setprogressbarmarquee)|設定的跑馬燈列`CTaskDialog`並將它加入至對話方塊。|  
|[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)|調整進度列的位置。|  
|[CTaskDialog::SetProgressBarRange](#setprogressbarrange)|調整進度列的範圍。|  
|[CTaskDialog::SetProgressBarState](#setprogressbarstate)|設定進度列狀態，並將它顯示在`CTaskDialog`。|  
|[CTaskDialog::SetRadioButtonOptions](#setradiobuttonoptions)|啟用或停用選項按鈕。|  
|[CTaskDialog::SetVerificationCheckbox](#setverificationcheckbox)|設定驗證 核取方塊的核取的狀態。|  
|[CTaskDialog::SetVerificationCheckboxText](#setverificationcheckboxtext)|設定驗證 核取方塊右邊的文字。|  
|[CTaskDialog::SetWindowTitle](#setwindowtitle)|設定標題`CTaskDialog`。|  
|[CTaskDialog::ShowDialog](#showdialog)|建立並顯示`CTaskDialog`。|  
|[CTaskDialog::TaskDialogCallback](#taskdialogcallback)|架構會呼叫這以回應各種 Windows 訊息。|  
  
### <a name="data-members"></a>資料成員  
  
|||  
|-|-|  
|`m_aButtons`|命令按鈕控制項的陣列`CTaskDialog`。|  
|`m_aRadioButtons`|陣列的選項按鈕控制項的`CTaskDialog`。|  
|`m_bVerified`|`TRUE`表示驗證 核取方塊。`FALSE`表示它不是。|  
|`m_footerIcon`|在頁尾中的圖示`CTaskDialog`。|  
|`m_hWnd`|視窗的控制代碼`CTaskDialog`。|  
|`m_mainIcon`|主要圖示`CTaskDialog`。|  
|`m_nButtonDisabled`|遮罩，表示其中一個常見的按鈕會停用。|  
|`m_nButtonElevation`|遮罩，表示其中一個常見的按鈕需要 UAC 提高權限。|  
|`m_nButtonId`|選取的命令按鈕控制項的識別碼。|  
|`m_nCommonButton`|遮罩，表示哪些常見的按鈕會顯示在`CTaskDialog`。|  
|`m_nDefaultCommandControl`|命令按鈕的 ID 控制，當選取`CTaskDialog`隨即出現。|  
|`m_nDefaultRadioButton`|識別碼的選項按鈕控制項，當選取`CTaskDialog`隨即出現。|  
|`m_nFlags`|遮罩，表示的選項`CTaskDialog`。|  
|`m_nProgressPos`|進度列目前的位置。  這個值必須介於 `m_nProgressRangeMin` 和 `m_nProgressRangeMax` 之間。|  
|`m_nProgressRangeMax`|進度列最大值。|  
|`m_nProgressRangeMin`|進度列最小值。|  
|`m_nProgressState`|進度列狀態。 如需詳細資訊，請參閱[CTaskDialog::SetProgressBarState](#setprogressbarstate)。|  
|`m_nRadioId`|選取的選項按鈕控制項的識別碼。|  
|`m_nWidth`|寬度`CTaskDialog`像素為單位。|  
|`m_strCollapse`|字串`CTaskDialog`時隱藏展開的資訊擴充方塊右邊的顯示。|  
|`m_strContent`|內容字串`CTaskDialog`。|  
|`m_strExpand`|字串`CTaskDialog`時展開的資訊會顯示擴充方塊右邊的顯示。|  
|`m_strFooter`|頁尾`CTaskDialog`。|  
|`m_strInformation`|擴充的資訊`CTaskDialog`。|  
|`m_strMainInstruction`|主要指示`CTaskDialog`。|  
|`m_strTitle`|標題`CTaskDialog`。|  
|`m_strVerification`|字串，`CTaskDialog`右邊的 [驗證] 核取方塊會顯示。|  
  
## <a name="remarks"></a>備註  
 `CTaskDialog`類別取代標準 Windows 訊息方塊，並具有其他功能，例如新的控制項，從使用者收集資訊。 這個類別是 MFC 程式庫中[!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]。 `CTaskDialog`從開始提供[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]。 舊版 Windows 無法顯示`CTaskDialog`物件。 使用`CTaskDialog::IsSupported`來判斷在執行階段目前的使用者是否可以顯示工作對話方塊。 標準 Windows 訊息方塊中仍然支援[!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)]。  
  
 `CTaskDialog`可僅當您建置應用程式使用 Unicode 程式庫。  
  
 `CTaskDialog`有兩個不同的建構函式。 一個建構函式可讓您指定兩個命令按鈕和六個規則的按鈕控制項的最大值。 在建立之後，您可以加入更多的命令按鈕`CTaskDialog`。 第二個建構函式不支援任何命令按鈕，但是您可以加入無限的數量的一般按鈕控制項。 如需建構函式的詳細資訊，請參閱[CTaskDialog::CTaskDialog](#ctaskdialog)。  
  
 下圖顯示範例`CTaskDialog`說明的某些控制項的位置。  
  
 ![CTaskDialog 範例](../../mfc/reference/media/ctaskdialogsample.png "ctaskdialogsample")  
CTaskDialog 範例  
  
## <a name="requirements"></a>需求  
 **最小必要作業系統︰**[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **標頭︰** afxtaskdialog.h  
  
##  <a name="addcommandcontrol"></a>CTaskDialog::AddCommandControl  
 加入新的命令按鈕控制項以`CTaskDialog`。  
  
```  
void AddCommandControl(
    int nCommandControlID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>參數  
 [in] `nCommandControlID`  
 命令控制項識別碼。  
  
 [in] `strCaption`  
 字串，`CTaskDialog`向使用者顯示。 使用此字串來說明命令的目的。  
  
 [in] `bEnabled`  
 布林值參數，指出是否啟用或停用 [新增] 按鈕。  
  
 [in] `bRequiresElevation`  
 布林值參數，指出命令是否需要提高權限。  
  
### <a name="remarks"></a>備註  
 `CTaskDialog Class`可以顯示無限的數量的命令按鈕控制項。 不過，如果`CTaskDialog`顯示任何命令按鈕控制項，它可以顯示六個按鈕的最大值。 如果`CTaskDialog`有沒有命令按鈕控制項，它可以顯示的按鈕數目沒有限制。  
  
 當使用者選取命令按鈕控制項，`CTaskDialog`關閉。 如果您的應用程式會顯示對話方塊中使用[CTaskDialog::DoModal](#domodal)，`DoModal`傳回`nCommandControlID`選取的命令按鈕控制項。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="addradiobutton"></a>CTaskDialog::AddRadioButton  
 加入選項按鈕， `CTaskDialog`。  
  
```  
void CTaskDialog::AddRadioButton(
    int nRadioButtonID,  
    const CString& strCaption,  
    BOOL bEnabled = TRUE);
```  
  
### <a name="parameters"></a>參數  
 [in] `nRadioButtonID`  
 選項按鈕的識別碼。  
  
 [in] `strCaption`  
 字串，`CTaskDialog`旁邊的選項按鈕會顯示。  
  
 [in] `bEnabled`  
 布林值參數，指出是否已啟用的選項按鈕。  
  
### <a name="remarks"></a>備註  
 選項按鈕[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)可讓您從使用者收集資訊。 使用函數[CTaskDialog::GetSelectedRadioButtonID](#getselectedradiobuttonid)來決定要選取哪一個按鈕。  
  
 `CTaskDialog`不需要`nRadioButtonID`參數都是唯一的每個選項按鈕。 不過，您可能會遇到未預期的行為，如果您不使用每個選項按鈕的相異識別項。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="clickcommandcontrol"></a>CTaskDialog::ClickCommandControl  
 以程式設計的方式，請按一下命令按鈕控制項或常見的按鈕。  
  
```  
protected:  
void ClickCommandControl(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `nCommandControlID`  
 按一下控制項的命令識別碼。  
  
### <a name="remarks"></a>備註  
 這個方法會產生 windows 訊息`TDM_CLICK_BUTTON`。  
  
##  <a name="clickradiobutton"></a>CTaskDialog::ClickRadioButton  
 以程式設計方式按一下選項按鈕。  
  
```  
protected:  
void ClickRadioButton(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `nRadioButtonID`  
 按一下選項按鈕的識別碼。  
  
### <a name="remarks"></a>備註  
 這個方法會產生 windows 訊息`TDM_CLICK_RADIO_BUTTON`。  
  
##  <a name="ctaskdialog"></a>CTaskDialog::CTaskDialog  
 建立的執行個體[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)。  
  
```  
CTaskDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nCommonButtons = TDCBF_OK_BUTTON | TDCBF_CANCEL_BUTTON,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));

 
CTaskDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast,  
    int nCommonButtons,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));
```  
  
### <a name="parameters"></a>參數  
 [in] `strContent`  
 若要使用內容的字串`CTaskDialog`。  
  
 [in] `strMainInstruction`  
 主要指示`CTaskDialog`。  
  
 [in] `strTitle`  
 標題`CTaskDialog`。  
  
 [in] `nCommonButtons`  
 要加入至一般按鈕的遮罩`CTaskDialog`。  
  
 [in] `nTaskDialogOptions`  
 一組選項用於`CTaskDialog`。  
  
 [in] `strFooter`  
 要做為頁尾的字串。  
  
 [in] `nIDCommandControlsFirst`  
 第一個命令字串識別碼。  
  
 [in] `nIDCommandControlsLast`  
 最後一個命令字串識別碼。  
  
### <a name="remarks"></a>備註  
 有兩種方式，您可以加入`CTaskDialog`您的應用程式。 第一種方式是使用其中一個建構函式來建立`CTaskDialog`，並顯示使用[CTaskDialog::DoModal](#domodal)。 第二種方式是使用靜態函式[CTaskDialog::ShowDialog](#showdialog)，可讓您顯示`CTaskDialog`不需要明確建立`CTaskDialog`物件。  
  
 第二個建構函式會使用您的應用程式的資源檔中的資料來建立命令按鈕控制項。 字串資料表資源檔中的有數個字串與相關聯的字串識別碼。 此方法會將命令按鈕控制項的每個有效的項目之間的字串資料表中`nIDCommandControlsFirst`和`nCommandControlsLast`(含） 之間。 這些命令按鈕控制項，字串資料表中的字串是控制項的標題和字串 ID 是控制項的 id。  
  
 請參閱[CTaskDialog::SetOptions](#setoptions)取得一份有效的選項。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="domodal"></a>CTaskDialog::DoModal  
 顯示`CTaskDialog`並使其成為強制回應。  
  
```  
INT_PTR DoModal (HWND hParent = ::GetActiveWindow());
```  
  
### <a name="parameters"></a>參數  
 [in] `hParent`  
 父視窗`CTaskDialog`。  
  
### <a name="return-value"></a>傳回值  
 對應至使用者所做的選取範圍的整數。  
  
### <a name="remarks"></a>備註  
 顯示的這個執行個體[CTaskDialog](../../mfc/reference/ctaskdialog-class.md)。 接著，應用程式等待使用者關閉對話方塊。  
  
 `CTaskDialog`當使用者選取一個常見的按鈕命令連結控制項，或關閉時，關閉`CTaskDialog`。 傳回值會指示使用者如何關閉此對話方塊的識別項。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getcommonbuttoncount"></a>CTaskDialog::GetCommonButtonCount  
 擷取通用的按鈕數目。  
  
```  
int GetCommonButtonCount() const;  
```  
  
### <a name="return-value"></a>傳回值  
 可用的通用按鈕數目。  
  
### <a name="remarks"></a>備註  
 常見的按鈕都將為您提供的預設按鈕[CTaskDialog::CTaskDialog](#ctaskdialog)。 [CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)會顯示對話方塊底部的按鈕。  
  
 CommCtrl.h 中，會提供按鈕的列舉的清單。  
  
##  <a name="getcommonbuttonflag"></a>CTaskDialog::GetCommonButtonFlag  
 將一般的按鈕類型的 [Windows] 按鈕相關聯的標準轉換[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)。  
  
```  
int GetCommonButtonFlag(int nButtonId) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `nButtonId`  
 標準 Windows 按鈕的值。  
  
### <a name="return-value"></a>傳回值  
 對應值`CTaskDialog`一般按鈕。 如果沒有任何對應的一般按鈕，這個方法會傳回 0。  
  
##  <a name="getcommonbuttonid"></a>CTaskDialog::GetCommonButtonId  
 將轉換其中一個常見的按鈕類型相關聯[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)標準 Windows 按鈕。  
  
```  
int GetCommonButtonId(int nFlag);
```  
  
### <a name="parameters"></a>參數  
 [in] `nFlag`  
 常見的按鈕類型相關聯的`CTaskDialog`類別。  
  
### <a name="return-value"></a>傳回值  
 對應的標準 Windows 按鈕的值。 如果沒有任何對應的 Windows 按鈕，則方法會傳回 0。  
  
##  <a name="getoptions"></a>CTaskDialog::GetOptions  
 傳回這個選項旗標`CTaskDialog`。  
  
```  
int GetOptions() const;  
```  
  
### <a name="return-value"></a>傳回值  
 旗標`CTaskDialog`。  
  
### <a name="remarks"></a>備註  
 如需有關可用的選項[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)，請參閱[CTaskDialog::SetOptions](#setoptions)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="getselectedcommandcontrolid"></a>CTaskDialog::GetSelectedCommandControlID  
 傳回選取的命令按鈕控制項。  
  
```  
int GetSelectedCommandControlID() const;  
```  
  
### <a name="return-value"></a>傳回值  
 目前選取的命令按鈕控制項的識別碼。  
  
### <a name="remarks"></a>備註  
 您沒有使用這個方法來擷取使用者選取的命令按鈕的識別碼。 該識別碼會傳回由[CTaskDialog::DoModal](#domodal)或[CTaskDialog::ShowDialog](#showdialog)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="getselectedradiobuttonid"></a>CTaskDialog::GetSelectedRadioButtonID  
 傳回選取的選項按鈕。  
  
```  
int GetSelectedRadioButtonID() const;  
```  
  
### <a name="return-value"></a>傳回值  
 選取的選項按鈕的識別碼。  
  
### <a name="remarks"></a>備註  
 使用者關閉對話方塊，來擷取選取的選項按鈕後，您可以使用這個方法。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="getverificationcheckboxstate"></a>CTaskDialog::GetVerificationCheckboxState  
 擷取驗證 核取方塊的狀態。  
  
```  
BOOL GetVerificationCheckboxState() const;  
```  
  
### <a name="return-value"></a>傳回值  
 `TRUE`如果勾選此核取方塊，則`FALSE`如果不是。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="iscommandcontrolenabled"></a>CTaskDialog::IsCommandControlEnabled  
 判斷是否已啟用命令按鈕控制項或按鈕。  
  
```  
BOOL IsCommandControlEnabled(int nCommandControlID) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `nCommandControlID`  
 若要測試的命令按鈕控制項或按鈕 ID。  
  
### <a name="return-value"></a>傳回值  
 `TRUE`如果控制項已啟用，`FALSE`如果不是。  
  
### <a name="remarks"></a>備註  
 您可以使用這個方法來判斷同時命令按鈕控制項的可用性和一般按鈕的`CTaskDialog Class`。  
  
 如果`nCommandControlID`不是有效的識別項，其中一個一般`CTaskDialog`按鈕或命令按鈕控制項，這個方法會擲回例外狀況。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="isradiobuttonenabled"></a>CTaskDialog::IsRadioButtonEnabled  
 判斷是否已啟用的選項按鈕。  
  
```  
BOOL IsRadioButtonEnabled(int nRadioButtonID) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `nRadioButtonID`  
 若要測試的選項按鈕的識別碼。  
  
### <a name="return-value"></a>傳回值  
 `TRUE`如果已啟用的選項按鈕，`FALSE`如果不是。  
  
### <a name="remarks"></a>備註  
 如果`nRadioButtonID`不是有效的識別項的選項按鈕，這個方法會擲回例外狀況。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="issupported"></a>CTaskDialog::IsSupported  
 判斷是否正在執行的應用程式的電腦支援`CTaskDialog`。  
  
```  
static BOOL IsSupported();
```  
  
### <a name="return-value"></a>傳回值  
 `TRUE`如果電腦支援`CTaskDialog`;`FALSE`否則。  
  
### <a name="remarks"></a>備註  
 使用此函數來判斷在執行階段，如果執行您的應用程式的電腦支援`CTaskDialog Class`。 如果電腦不支援`CTaskDialog`，您應該提供通訊的資訊給使用者的另一種方法。 您的應用程式將會損毀，如果它嘗試使用`CTaskDialog`不支援的電腦上`CTaskDialog`類別。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="loadcommandcontrols"></a>CTaskDialog::LoadCommandControls  
 使用字串資料表中的資料，以新增命令按鈕控制項。  
  
```  
void LoadCommandControls(
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast);
```  
  
### <a name="parameters"></a>參數  
 [in] `nIDCommandControlsFirst`  
 第一個命令字串識別碼。  
  
 [in] `nIDCommandControlsLast`  
 最後一個命令字串識別碼。  
  
### <a name="remarks"></a>備註  
 這個方法會從您的應用程式的資源檔案使用資料來建立命令按鈕控制項。 字串資料表資源檔中的有數個字串與相關聯的字串識別碼。 使用此方法加入的新命令按鈕控制項使用字串控制項的標題字串 ID，控制項的 id。 所提供的字串選取範圍`nIDCommandControlsFirst`和`nCommandControlsLast`(含） 之間。 如果範圍中的空項目，此方法不會新增該項目的命令按鈕控制項。  
  
 根據預設，新的命令按鈕控制項都已啟用，並不需要提升權限。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="loadradiobuttons"></a>CTaskDialog::LoadRadioButtons  
 使用字串資料表中的資料，以新增選項按鈕控制項。  
  
```  
void LoadRadioButtons(
    int nIDRadioButtonsFirst,  
    int nIDRadioButtonsLast);
```  
  
### <a name="parameters"></a>參數  
 [in] `nIDRadioButtonsFirst`  
 第一個選項按鈕的字串識別碼。  
  
 [in] `nIDRadioButtonsLast`  
 最後一個選項按鈕的字串識別碼。  
  
### <a name="remarks"></a>備註  
 這個方法會從您的應用程式的資源檔使用的資料建立選項按鈕。 字串資料表資源檔中的有數個字串與相關聯的字串識別碼。 使用此方法加入新的選項按鈕的選項按鈕的標題和字串 ID 使用字串，選項按鈕的識別碼。 所提供的字串選取範圍`nIDRadioButtonsFirst`和`nRadioButtonsLast`(含） 之間。 如果範圍中的空項目，此方法不會新增該項目的選項按鈕。  
  
 根據預設，會啟用新的選項按鈕。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="navigateto"></a>CTaskDialog::NavigateTo  
 將焦點轉移到另一個`CTaskDialog`。  
  
```  
protected:  
void NavigateTo(CTaskDialog& oTaskDialog) const;  
```  
  
### <a name="parameters"></a>參數  
 [in] `oTaskDialog`  
 `CTaskDialog`接收焦點。  
  
### <a name="remarks"></a>備註  
 這個方法會隱藏目前`CTaskDialog`當顯示`oTaskDialog`。 `oTaskDialog`會顯示在相同的位置與目前`CTaskDialog`。  
  
##  <a name="oncommandcontrolclick"></a>CTaskDialog::OnCommandControlClick  
 當使用者按一下的命令按鈕控制項，架構會呼叫這個方法。  
  
```  
virtual HRESULT OnCommandControlClick(int nCommandControlID);
```  
  
### <a name="parameters"></a>參數  
 [in] `nCommandControlID`  
 使用者選取命令按鈕控制項的識別碼。  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="oncreate"></a>CTaskDialog::OnCreate  
 建立之後，架構會呼叫這個方法`CTaskDialog`。  
  
```  
virtual HRESULT OnCreate();
```  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="ondestroy"></a>CTaskDialog::OnDestroy  
 架構會呼叫這個方法，它會終結之前，立即`CTaskDialog`。  
  
```  
virtual HRESULT OnDestroy();
```  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="onexpandbuttonclick"></a>CTaskDialog::OnExpandButtonClick  
 當使用者按一下 [展開] 按鈕時，架構會呼叫這個方法。  
  
```  
virtual HRESULT OnExpandButtonClicked(BOOL bExpanded);
```  
  
### <a name="parameters"></a>參數  
 [in] `bExpanded`  
 非零值表示會顯示額外的資訊。0 表示隱藏的額外資訊。  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="onhelp"></a>CTaskDialog::OnHelp  
 當使用者要求說明時，架構會呼叫這個方法。  
  
```  
virtual HRESULT OnHelp();
```  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="onhyperlinkclick"></a>CTaskDialog::OnHyperlinkClick  
 當使用者按一下超連結時，架構會呼叫這個方法。  
  
```  
virtual HRESULT OnHyperlinkClick(const CString& strHref);
```  
  
### <a name="parameters"></a>參數  
 [in] `strHref`  
 字串，代表超連結。  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 這個方法會呼叫[ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153)它會傳回前`S_OK`。  
  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="oninit"></a>CTaskDialog::OnInit  
 架構會呼叫這個方法時`CTaskDialog`已初始化。  
  
```  
virtual HRESULT OnInit();
```  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="onnavigatepage"></a>CTaskDialog::OnNavigatePage  
 架構會呼叫這個方法以回應[CTaskDialog::NavigateTo](#navigateto)方法。  
  
```  
virtual HRESULT OnNavigatePage();
```  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="onradiobuttonclick"></a>CTaskDialog::OnRadioButtonClick  
 當使用者選取選項按鈕控制項，架構會呼叫這個方法。  
  
```  
virtual HRESULT OnRadioButtonClick(int nRadioButtonID);
```  
  
### <a name="parameters"></a>參數  
 [in] `nRadioButtonID`  
 使用者已按一下選項按鈕控制項的識別碼。  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="ontimer"></a>CTaskDialog::OnTimer  
 在計時器逾時，架構會呼叫這個方法。  
  
```  
virtual HRESULT OnTimer(long lTime);
```  
  
### <a name="parameters"></a>參數  
 [in] `lTime`  
 時間以來的毫秒數`CTaskDialog`建立或計時器重設。  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="onverificationcheckboxclick"></a>CTaskDialog::OnVerificationCheckboxClick  
 當使用者按一下 [驗證] 核取方塊，架構會呼叫這個方法。  
  
```  
virtual HRESULT OnVerificationCheckboxClick(BOOL bChecked);
```  
  
### <a name="parameters"></a>參數  
 [in] `bChecked`  
 `TRUE`表示已選取 [驗證] 核取方塊。`FALSE`表示它不是。  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 覆寫這個方法在衍生類別來實作自訂行為。  
  
##  <a name="removeallcommandcontrols"></a>CTaskDialog::RemoveAllCommandControls  
 移除所有的命令按鈕控制項從`CTaskDialog`。  
  
```  
void RemoveAllCommandControls();
```  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="removeallradiobuttons"></a>CTaskDialog::RemoveAllRadioButtons  
 移除所有選項按鈕，從`CTaskDialog`。  
  
```  
void RemoveAllRadioButtons();
```  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setcommandcontroloptions"></a>CTaskDialog::SetCommandControlOptions  
 更新命令按鈕控制項上`CTaskDialog`。  
  
```  
void SetCommandControlOptions(
    int nCommandControlID,  
    BOOL bEnabled,  
    BOOL bRequiresElevation = FALSE);
```  
  
### <a name="parameters"></a>參數  
 [in] `nCommandControlID`  
 若要更新命令控制項 ID。  
  
 [in] `bEnabled`  
 表示如果啟用或停用指定的命令按鈕控制項的布林參數。  
  
 [in] `bRequiresElevation`  
 布林值參數，指出是否指定的命令按鈕控制項需要提高權限。  
  
### <a name="remarks"></a>備註  
 使用這個方法來變更是否已啟用命令按鈕控制項，或需要提高權限之後加入至, `CTaskDialog Class`。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setcommonbuttonoptions"></a>CTaskDialog::SetCommonButtonOptions  
 更新通用的按鈕，來啟用，並需要 UAC 提高權限的子集。  
  
```  
void SetCommonButtonOptions(
    int nDisabledButtonMask,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>參數  
 [in] `nDisabledButtonMask`  
 若要停用，一般按鈕的遮罩。  
  
 [in] `nElevationButtonMask`  
 需要提高權限的一般按鈕遮罩。  
  
### <a name="remarks"></a>備註  
 您可以設定可用的一般按鈕的執行個體[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)使用建構函式[CTaskDialog::CTaskDialog](#ctaskdialog)和方法[CTaskDialog::SetCommonButtons](#setcommonbuttons)。 `CTaskDialog::SetCommonButtonOptions`不支援加入新的一般按鈕。  
  
 如果您使用這個方法來停用，或提高權限不適用於這一般按鈕`CTaskDialog`，使用這個方法擲回的例外狀況[請](diagnostic-services.md#ensure)巨集。  
  
 這個方法會啟用可用於任何按鈕`CTaskDialog`但不在`nDisabledButtonMask`，即使之前已停用。 這個方法會以類似的方式將提高權限︰ 它會記錄為一般按鈕是否可用，但不是包含在不需要提高權限的一般按鈕`nElevationButtonMask`。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcommonbuttons"></a>CTaskDialog::SetCommonButtons  
 加入至一般按鈕`CTaskDialog`。  
  
```  
void SetCommonButtons(
    int nButtonMask,  
    int nDisabledButtonMask = 0,  
    int nElevationButtonMask = 0);
```  
  
### <a name="parameters"></a>參數  
 [in] `nButtonMask`  
 要加入至按鈕遮罩`CTaskDialog`。  
  
 [in] `nDisabledButtonMask`  
 若要停用按鈕的遮罩。  
  
 [in] `nElevationButtonMask`  
 遮罩需要提高權限的按鈕。  
  
### <a name="remarks"></a>備註  
 您之後無法呼叫這個方法顯示在視窗中的這個執行個體`CTaskDialog Class`建立。 如果您這樣做，這個方法會擲回例外狀況。  
  
 按鈕以`nButtonMask`覆寫先前已加入至任何一般按鈕`CTaskDialog`。 只有按鈕所示`nButtonMask`可用。  
  
 如果有任一個`nDisabledButtonMask`或`nElevationButtonMask`包含未出現在按鈕`nButtonMask`，使用這個方法擲回的例外狀況[請](diagnostic-services.md#ensure)巨集。  
  
 根據預設，所有的一般按鈕已啟用，而且不需要提升權限。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 6](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_6.cpp)]  
  
##  <a name="setcontent"></a>CTaskDialog::SetContent  
 更新的內容`CTaskDialog`。  
  
```  
void SetContent(const CString& strContent);
```  
  
### <a name="parameters"></a>參數  
 [in] `strContent`  
 要向使用者顯示的字串。  
  
### <a name="remarks"></a>備註  
 內容`CTaskDialog Class`是使用者在對話方塊中的主要區段中顯示的文字。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setdefaultcommandcontrol"></a>CTaskDialog::SetDefaultCommandControl  
 指定的預設命令按鈕控制項。  
  
```  
void SetDefaultCommandControl(int nCommandControlID);
```  
  
### <a name="parameters"></a>參數  
 [in] `nCommandControlID`  
 設為預設命令按鈕控制項的識別碼。  
  
### <a name="remarks"></a>備註  
 預設命令按鈕控制項是控制項時選取`CTaskDialog`先顯示給使用者。  
  
 這個方法擲回例外狀況，如果找不到所指定的命令按鈕控制項`nCommandControlID`。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 2](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_1.cpp)]  
  
##  <a name="setdefaultradiobutton"></a>CTaskDialog::SetDefaultRadioButton  
 指定的預設選項按鈕。  
  
```  
void SetDefaultRadioButton(int nRadioButtonID);
```  
  
### <a name="parameters"></a>參數  
 [in] `nRadioButtonID`  
 設為預設的選項按鈕的識別碼。  
  
### <a name="remarks"></a>備註  
 預設選項按鈕是為按鈕時選取`CTaskDialog`先顯示給使用者。  
  
 這個方法擲回例外狀況，如果找不到所指定的選項按鈕`nRadioButtonID`。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setdialogwidth"></a>CTaskDialog::SetDialogWidth  
 調整的寬度， `CTaskDialog`。  
  
```  
void SetDialogWidth(int nWidth = 0);
```  
  
### <a name="parameters"></a>參數  
 [in] `nWidth`  
 對話方塊中，單位為像素寬度。  
  
### <a name="remarks"></a>備註  
 參數`nWidth`必須大於或等於 0。 否則，這個方法會擲回例外狀況。  
  
 如果`nWidth`設為 0，這個方法會設定對話方塊的預設大小。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setexpansionarea"></a>CTaskDialog::SetExpansionArea  
 更新的擴充區域`CTaskDialog`。  
  
```  
void SetExpansionArea(
    const CString& strExpandedInformation,  
    const CString& strCollapsedLabel = _T(""),  
    const CString& strExpandedLabel = _T(""));
```  
  
### <a name="parameters"></a>參數  
 [in] `strExpandedInformation`  
 字串，`CTaskDialog`顯示在對話方塊中的主要本文中，當使用者按一下 [展開] 按鈕。  
  
 [in] `strCollapsedLabel`  
 字串，`CTaskDialog`擴充的區域是否摺疊時，[擴充] 按鈕旁邊會顯示。  
  
 [in] `strExpandedLabel`  
 字串，`CTaskDialog`時展開的區域會顯示 [展開] 按鈕旁邊會顯示。  
  
### <a name="remarks"></a>備註  
 擴充區域`CTaskDialog Class`可讓您提供其他資訊給使用者。 擴充區域位於的主要部分`CTaskDialog`位於立即下方的標題與內容的字串。  
  
 當`CTaskDialog`這是第一次顯示，不會顯示已展開的資訊以及將`strCollapsedLabel`旁 [展開] 按鈕。 當使用者按一下展開按鈕`CTaskDialog`顯示`strExpandedInformation`並變更標籤`strExpandedLabel`。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootericon"></a>CTaskDialog::SetFooterIcon  
 更新的頁尾圖示`CTaskDialog`。  
  
```  
void SetFooterIcon(HICON hFooterIcon);  
void SetFooterIcon(LPCWSTR lpszFooterIcon);
```  
  
### <a name="parameters"></a>參數  
 [in] `hFooterIcon`  
 新圖示`CTaskDialog`。  
  
 [in] `lpszFooterIcon`  
 新圖示`CTaskDialog`。  
  
### <a name="remarks"></a>備註  
 頁尾圖示會顯示在底部[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)。 它可以有關聯的頁尾文字。 您可以變更具有頁尾文字[CTaskDialog::SetFooterText](#setfootertext)。  
  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集如果`CTaskDialog`會顯示輸入的參數是否`NULL`。  
  
 A`CTaskDialog`只能接受`HICON`或`LPCWSTR`為頁尾的圖示。 這設定設定選項`TDF_USE_HICON_FOOTER`建構函式或[CTaskDialog::SetOptions](#setoptions)。 根據預設，`CTaskDialog`設定為使用`LPCWSTR`作為 [頁尾] 圖示的輸入型別。 如果您嘗試設定使用的不適當類型的圖示，這個方法會產生例外狀況。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setfootertext"></a>CTaskDialog::SetFooterText  
 更新上頁尾的文字`CTaskDialog`。  
  
```  
void SetFooterText(const CString& strFooterText);
```  
  
### <a name="parameters"></a>參數  
 [in] `strFooterText`  
 新的頁尾文字。  
  
### <a name="remarks"></a>備註  
 在底部的頁尾文字旁邊的 [頁尾] 圖示會出現`CTaskDialog`。 您可以變更 [頁尾] 圖示以[CTaskDialog::SetFooterIcon](#setfootericon)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmainicon"></a>CTaskDialog::SetMainIcon  
 更新的主要圖示`CTaskDialog`。  
  
```  
void SetMainIcon(HICON hMainIcon);  
void SetMainIcon(LPCWSTR lpszMainIcon);
```  
  
### <a name="parameters"></a>參數  
 [in] `hMainIcon`  
 [新增] 圖示。  
  
 [in] `lpszMainIcon`  
 [新增] 圖示。  
  
### <a name="remarks"></a>備註  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集如果`CTaskDialog`會顯示輸入的參數是否`NULL`。  
  
 A`CTaskDialog`只能接受`HICON`或`LPCWSTR`做為主要的圖示。 您可以設定此設定`TDF_USE_HICON_MAIN`選項在建構函式中或[CTaskDialog::SetOptions](#setoptions)方法。 根據預設，`CTaskDialog`設定為使用`LPCWSTR`做為主要圖示的輸入類型。 如果您嘗試設定使用的不適當類型的圖示，這個方法會產生例外狀況。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setmaininstruction"></a>CTaskDialog::SetMainInstruction  
 更新的主要指示`CTaskDialog`。  
  
```  
void SetMainInstruction(const CString& strInstructions);
```  
  
### <a name="parameters"></a>參數  
 [in] `strInstructions`  
 新的主要指示。  
  
### <a name="remarks"></a>備註  
 主要指示`CTaskDialog Class`是大型的粗體字中對使用者顯示的文字。 它位於對話方塊的標題列下方。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setoptions"></a>CTaskDialog::SetOptions  
 會設定的選項`CTaskDialog`。  
  
```  
void SetOptions(int nOptionFlag);
```  
  
### <a name="parameters"></a>參數  
 [in] `nOptionFlag`  
 旗標，以用於一組`CTaskDialog`。  
  
### <a name="remarks"></a>備註  
 這個方法會清除所有的目前選項`CTaskDialog`。 若要保留目前的選項，您必須在擷取第一次與[CTaskDialog::GetOptions](#getoptions)將它們結合為您想要設定的選項。  
  
 下表列出所有有效的選項。  
  
 `TDF_ENABLE_HYPERLINKS`  
 中的超連結可讓`CTaskDialog`。  
  
 `TDF_USE_HICON_MAIN`  
 設定`CTaskDialog`使用`HICON`主要圖示。 若要使用的替代方案是`LPCWSTR`。  
  
 `TDF_USE_HICON_FOOTER`  
 設定`CTaskDialog`使用`HICON`頁尾圖示。 若要使用的替代方案是`LPCWSTR`。  
  
 `TDF_ALLOW_DIALOG_CANCELLATION`  
 可讓使用者關閉`CTaskDialog`使用鍵盤，或使用中的對話方塊中，右上角的圖示即使**取消**按鈕未啟用。 如果未設定此旗標和**取消**按鈕未啟用，使用者無法使用 Alt + F4，Esc 鍵，關閉對話方塊或標題列的關閉按鈕。  
  
 `TDF_USE_COMMAND_LINKS`  
 設定`CTaskDialog`用於命令按鈕控制項。  
  
 `TDF_USE_COMMAND_LINKS_NO_ICON`  
 設定`CTaskDialog`用於命令按鈕控制項而不會顯示在控制項旁邊的圖示。 `TDF_USE_COMMAND_LINKS` 會覆寫 `TDF_USE_COMMAND_LINKS_NO_ICON`。  
  
 `TDF_EXPAND_FOOTER_AREA`  
 表示目前已擴充擴充區域。  
  
 `TDF_EXPANDED_BY_DEFAULT`  
 決定預設是否展開擴充區域。  
  
 `TDF_VERIFICATION_FLAG_CHECKED`  
 表示目前已選取 [驗證] 核取方塊。  
  
 `TDF_SHOW_PROGRESS_BAR`  
 設定`CTaskDialog`顯示進度列。  
  
 `TDF_SHOW_MARQUEE_PROGRESS_BAR`  
 設定進度列是跑馬燈進度列。 如果您啟用此選項時，您必須設定`TDF_SHOW_PROGRESS_BAR`具有預期的行為。  
  
 `TDF_CALLBACK_TIMER`  
 表示`CTaskDialog`回呼間隔設定為約 200 毫秒。  
  
 `TDF_POSITION_RELATIVE_TO_WINDOW`  
 設定`CTaskDialog`相對於父視窗置中對齊。 如果未啟用這個旗標，`CTaskDialog`相對於此監視會置中。  
  
 `TDF_RTL_LAYOUT`  
 設定`CTaskDialog`由右至左讀取的版面配置。  
  
 `TDF_NO_DEFAULT_RADIO_BUTTON`  
 表示已選取任何選項按鈕時`CTaskDialog`隨即出現。  
  
 `TDF_CAN_BE_MINIMIZED`  
 讓使用者可以最小化`CTaskDialog`。 若要支援此選項，`CTaskDialog`不可為強制回應。 MFC 不支援此選項，因為 MFC 不支援非強制回應`CTaskDialog`。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="setprogressbarmarquee"></a>CTaskDialog::SetProgressBarMarquee  
 設定的跑馬燈列`CTaskDialog`並將它加入至對話方塊。  
  
```  
void SetProgressBarMarquee(
    BOOL bEnabled = TRUE,  
    int nMarqueeSpeed = 0);
```  
  
### <a name="parameters"></a>參數  
 [in] `bEnabled`  
 `TRUE`若要啟用跑馬燈 列中。`FALSE`以停用跑馬燈列，並移除從`CTaskDialog`。  
  
 [in] `nMarqueeSpeed`  
 整數，表示跑馬燈列的速度。  
  
### <a name="remarks"></a>備註  
 跑馬燈列會顯示主要文字的底下`CTaskDialog Class`。  
  
 使用`nMarqueeSpeed`設定跑馬燈列; 的速度較大的值表示較慢的速度。 值為 0`nMarqueeSpeed`讓移動的預設速度跑馬燈列[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]。  
  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集如果`nMarqueeSpeed`小於 0。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarposition"></a>CTaskDialog::SetProgressBarPosition  
 調整進度列的位置。  
  
```  
void SetProgressBarPosition(int nProgressPos);
```  
  
### <a name="parameters"></a>參數  
 [in] `nProgressPos`  
 進度列位置。  
  
### <a name="remarks"></a>備註  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集如果`nProgressPos`不在進度列範圍內。 您可以變更與進度列範圍[CTaskDialog::SetProgressBarRange](#setprogressbarrange)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarrange"></a>CTaskDialog::SetProgressBarRange  
 調整進度列的範圍。  
  
```  
void SetProgressBarRange(
    int nRangeMin,  
    int nRangeMax);
```  
  
### <a name="parameters"></a>參數  
 [in] `nRangeMin`  
 進度列的下限。  
  
 [in] `nRangeMax`  
 進度列的上限。  
  
### <a name="remarks"></a>備註  
 進度列的位置是相對於`nRangeMin`和`nRangeMax`。 例如，如果`nRangeMin`為 50 和`nRangeMax`為 100、 75 的位置為偶數個進度列。 使用[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)設定進度列的位置。  
  
 若要顯示進度列選項`TDF_SHOW_PROGRESS_BAR`必須啟用並`TDF_SHOW_MARQUEE_PROGRESS_BAR`不能啟用。 這個方法會自動設定`TDF_SHOW_PROGRESS_BAR`並清除`TDF_SHOW_MARQUEE_PROGRESS_BAR`。 使用[CTaskDialog::SetOptions](#setoptions)手動變更這個執行個體的選項[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)。  
  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集如果`nRangeMin`是不小於`nRangeMax`。 這個方法也會擲回例外狀況如果`CTaskDialog`尚未顯示，且有跑馬燈進度列。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setprogressbarstate"></a>CTaskDialog::SetProgressBarState  
 設定進度列狀態，並將它顯示在`CTaskDialog`。  
  
```  
void SetProgressBarState(int nState = PBST_NORMAL);
```  
  
### <a name="parameters"></a>參數  
 [in] `nState`  
 進度列狀態。 請參閱 < 備註 > 一節提供可能的值。  
  
### <a name="remarks"></a>備註  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集如果`CTaskDialog`尚未顯示，且有跑馬燈進度列。  
  
 下表列出可能的值為`nState`。 在這些情況下，進度列會與標準的色彩填滿，直到達到指定的停駐點位置。 此時，它會變更狀態的色彩。  
  
 PBST_NORMAL  
 之後進度列填滿、`CTaskDialog`不會變更軸的色彩。 根據預設，標準的色彩為綠色。  
  
 PBST_ERROR  
 之後進度列填滿、`CTaskDialog`變成錯誤的色彩列的色彩。 根據預設，這是紅色。  
  
 PBST_PAUSED  
 之後進度列填滿、`CTaskDialog`列的色彩變更為 已暫停的色彩。 根據預設，這是黃色。  
  
 您可以設定在進度列，便停止[CTaskDialog::SetProgressBarPosition](#setprogressbarposition)。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 4](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_7.cpp)]  
  
##  <a name="setradiobuttonoptions"></a>CTaskDialog::SetRadioButtonOptions  
 啟用或停用選項按鈕。  
  
```  
void SetRadioButtonOptions(
    int nRadioButtonID,  
    BOOL bEnabled);
```  
  
### <a name="parameters"></a>參數  
 [in] `nRadioButtonID`  
 選項按鈕控制項的識別碼。  
  
 [in] `bEnabled`  
 `TRUE`若要啟用的選項按鈕。`FALSE`停用的選項按鈕。  
  
### <a name="remarks"></a>備註  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集如果`nRadioButtonID`不是有效的識別碼，此選項按鈕。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 3](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_2.cpp)]  
  
##  <a name="setverificationcheckbox"></a>CTaskDialog::SetVerificationCheckbox  
 設定驗證 核取方塊的核取的狀態。  
  
```  
void SetVerificationCheckbox(BOOL bChecked);
```  
  
### <a name="parameters"></a>參數  
 [in] `bChecked`  
 `TRUE`將 驗證 核取方塊時選取`CTaskDialog`隨即出現。`FALSE`能夠驗證 核取方塊未選取時`CTaskDialog`隨即出現。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setverificationcheckboxtext"></a>CTaskDialog::SetVerificationCheckboxText  
 設定右邊的 [驗證] 核取方塊會顯示的文字。  
  
```  
void SetVerificationCheckboxText(CString& strVerificationText);
```  
  
### <a name="parameters"></a>參數  
 [in] `strVerificationText`  
 這個方法會驗證核取方塊旁顯示的文字。  
  
### <a name="remarks"></a>備註  
 這個方法會擲回的例外狀況[請](diagnostic-services.md#ensure)巨集，如果這個執行個體`CTaskDialog Class`已顯示。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 5](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_4.cpp)]  
  
##  <a name="setwindowtitle"></a>CTaskDialog::SetWindowTitle  
 設定標題`CTaskDialog`。  
  
```  
void SetWindowTitle(CString& strWindowTitle);
```  
  
### <a name="parameters"></a>參數  
 [in] `strWindowTitle`  
 新標題`CTaskDialog`。  
  
### <a name="remarks"></a>備註  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 7](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_3.cpp)]  
  
##  <a name="showdialog"></a>CTaskDialog::ShowDialog  
 建立並顯示`CTaskDialog`。  
  
```  
static INT_PTR ShowDialog(
    const CString& strContent,  
    const CString& strMainInstruction,  
    const CString& strTitle,  
    int nIDCommandControlsFirst,  
    int nIDCommandControlsLast,  
    int nCommonButtons = TDCBF_YES_BUTTON | TDCBF_NO_BUTTON,  
    int nTaskDialogOptions = TDF_ENABLE_HYPERLINKS | TDF_USE_COMMAND_LINKS,  
    const CString& strFooter = _T(""));
```  
  
### <a name="parameters"></a>參數  
 [in] `strContent`  
 若要使用內容的字串`CTaskDialog`。  
  
 [in] `strMainInstruction`  
 主要指示`CTaskDialog`。  
  
 [in] `strTitle`  
 標題`CTaskDialog`。  
  
 [in] `nIDCommandControlsFirst`  
 第一個命令字串識別碼。  
  
 [in] `nIDCommandControlsLast`  
 最後一個命令字串識別碼。  
  
 [in] `nCommonButtons`  
 要加入至按鈕遮罩`CTaskDialog`。  
  
 [in] `nTaskDialogOptions`  
 一組選項用於`CTaskDialog`。  
  
 [in] `strFooter`  
 要做為頁尾的字串。  
  
### <a name="return-value"></a>傳回值  
 對應至使用者所做的選取範圍的整數。  
  
### <a name="remarks"></a>備註  
 這個靜態方法可讓您建立的執行個體`CTaskDialog Class`而不需要明確建立`CTaskDialog`程式碼中的物件。 因為沒有任何`CTaskDialog`物件，您無法呼叫任何其他方法的`CTaskDialog`如果您使用這個方法來顯示`CTaskDialog`給使用者。  
  
 這個方法會從您的應用程式的資源檔案使用資料來建立命令按鈕控制項。 字串資料表資源檔中的有數個字串與相關聯的字串識別碼。 此方法會將命令按鈕控制項的每個有效的項目之間的字串資料表中`nIDCommandControlsFirst`和`nCommandControlsLast`(含） 之間。 這些命令按鈕控制項，字串資料表中的字串是控制項的標題和字串 ID 是控制項的 id。  
  
 請參閱[CTaskDialog::SetOptions](#setoptions)取得一份有效的選項。  
  
 `CTaskDialog`當使用者選取一個常見的按鈕命令連結控制項，或關閉時，關閉`CTaskDialog`。 傳回值會指示使用者如何關閉此對話方塊的識別項。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFC_CTaskDialog # 1](../../mfc/reference/codesnippet/cpp/ctaskdialog-class_5.cpp)]  
  
##  <a name="taskdialogcallback"></a>CTaskDialog::TaskDialogCallback  
 架構會呼叫這個方法，以回應各種 Windows 訊息。  
  
```  
friend:  
HRESULT TaskDialogCallback(
    HWND hWnd,  
    UINT uNotification,  
    WPARAM wParam,  
    LPARAM lParam,  
    LONG_PTR dwRefData);
```  
  
### <a name="parameters"></a>參數  
 [in] `hwnd`  
 控制代碼`m_hWnd`結構`CTaskDialog`。  
  
 [in] `uNotification`  
 指定產生之訊息的通知程式碼。  
  
 [in] `wParam`  
 訊息的詳細資訊。  
  
 [in] `lParam`  
 訊息的詳細資訊。  
  
 [in] `dwRefData`  
 指標`CTaskDialog`回呼訊息所套用的物件。  
  
### <a name="return-value"></a>傳回值  
 取決於特定通知程式碼。 如需詳細資訊，請參閱＜備註＞一節。  
  
### <a name="remarks"></a>備註  
 預設實作`TaskDialogCallback`處理特定訊息，然後再呼叫之方法上的 適當[CTaskDialog 類別](../../mfc/reference/ctaskdialog-class.md)。 例如，以回應`TDN_BUTTON_CLICKED`訊息，`TaskDialogCallback`呼叫[CTaskDialog::OnCommandControlClick](#oncommandcontrolclick)。  
  
 值`wParam`和`lParam`取決於特定產生的訊息。 它是可將一個或兩個這些值可以是空的。 下表列出支援的預設通知和功能的值`wParam`和`lParam`代表。 如果您覆寫這個方法在衍生類別中的，您應該實作下表中的每個訊息的回呼程式碼。  
  
|通知訊息|`wParam` 值|`lParam` 值|  
|--------------------------|--------------------|--------------------|  
|`TDN_CREATED`|未使用。|未使用。|  
|`TDN_NAVIGATED`|未使用。|未使用。|  
|`TDN_BUTTON_CLICKED`|命令按鈕控制項的識別碼。|未使用。|  
|`TDN_HYPERLINK_CLICKED`|未使用。|A [LPCWSTR](http://msdn.microsoft.com/library/windows/desktop/aa383751)包含連結的結構。|  
|`TDN_TIMER`|時間以來的毫秒數`CTaskDialog`建立或計時器重設。|未使用。|  
|`TDN_DESTROYED`|未使用。|未使用。|  
|`TDN_RADIO_BUTTON_CLICKED`|選項按鈕 id。|未使用。|  
|`TDN_DIALOG_CONSTRUCTED`|未使用。|未使用。|  
|`TDN_VERIFICATION_CLICKED`|1，表示核取核取方塊，如果不是 0。|未使用。|  
|`TDN_HELP`|未使用。|未使用。|  
|`TDN_EXPANDO_BUTTON_CLICKED`|0，如果擴充區域摺疊。如果擴充文字會顯示為非零。|未使用。|  
  
## <a name="see-also"></a>另請參閱  
 [類別](../../mfc/reference/mfc-classes.md)   
 [CObject 類別](../../mfc/reference/cobject-class.md)   
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [逐步解說：將 CTaskDialog 新增至應用程式](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)



