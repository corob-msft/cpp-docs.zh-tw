---
title: "CDHtmlDialog 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDHtmlDialog
- AFXDHTML/CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CDHtmlDialog
- AFXDHTML/CDHtmlDialog::CanAccessExternal
- AFXDHTML/CDHtmlDialog::CreateControlSite
- AFXDHTML/CDHtmlDialog::DDX_DHtml_AxControl
- AFXDHTML/CDHtmlDialog::DDX_DHtml_CheckBox
- AFXDHTML/CDHtmlDialog::DDX_DHtml_ElementText
- AFXDHTML/CDHtmlDialog::DDX_DHtml_Radio
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectIndex
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectString
- AFXDHTML/CDHtmlDialog::DDX_DHtml_SelectValue
- AFXDHTML/CDHtmlDialog::DestroyModeless
- AFXDHTML/CDHtmlDialog::EnableModeless
- AFXDHTML/CDHtmlDialog::FilterDataObject
- AFXDHTML/CDHtmlDialog::GetControlDispatch
- AFXDHTML/CDHtmlDialog::GetControlProperty
- AFXDHTML/CDHtmlDialog::GetCurrentUrl
- AFXDHTML/CDHtmlDialog::GetDHtmlDocument
- AFXDHTML/CDHtmlDialog::GetDropTarget
- AFXDHTML/CDHtmlDialog::GetElement
- AFXDHTML/CDHtmlDialog::GetElementHtml
- AFXDHTML/CDHtmlDialog::GetElementInterface
- AFXDHTML/CDHtmlDialog::GetElementProperty
- AFXDHTML/CDHtmlDialog::GetElementText
- AFXDHTML/CDHtmlDialog::GetEvent
- AFXDHTML/CDHtmlDialog::GetExternal
- AFXDHTML/CDHtmlDialog::GetHostInfo
- AFXDHTML/CDHtmlDialog::GetOptionKeyPath
- AFXDHTML/CDHtmlDialog::HideUI
- AFXDHTML/CDHtmlDialog::IsExternalDispatchSafe
- AFXDHTML/CDHtmlDialog::LoadFromResource
- AFXDHTML/CDHtmlDialog::Navigate
- AFXDHTML/CDHtmlDialog::OnBeforeNavigate
- AFXDHTML/CDHtmlDialog::OnDocumentComplete
- AFXDHTML/CDHtmlDialog::OnDocWindowActivate
- AFXDHTML/CDHtmlDialog::OnFrameWindowActivate
- AFXDHTML/CDHtmlDialog::OnInitDialog
- AFXDHTML/CDHtmlDialog::OnNavigateComplete
- AFXDHTML/CDHtmlDialog::ResizeBorder
- AFXDHTML/CDHtmlDialog::SetControlProperty
- AFXDHTML/CDHtmlDialog::SetElementHtml
- AFXDHTML/CDHtmlDialog::SetElementProperty
- AFXDHTML/CDHtmlDialog::SetElementText
- AFXDHTML/CDHtmlDialog::SetExternalDispatch
- AFXDHTML/CDHtmlDialog::SetHostFlags
- AFXDHTML/CDHtmlDialog::ShowContextMenu
- AFXDHTML/CDHtmlDialog::ShowUI
- AFXDHTML/CDHtmlDialog::TranslateAccelerator
- AFXDHTML/CDHtmlDialog::TranslateUrl
- AFXDHTML/CDHtmlDialog::UpdateUI
- AFXDHTML/CDHtmlDialog::m_bUseHtmlTitle
- AFXDHTML/CDHtmlDialog::m_nHtmlResID
- AFXDHTML/CDHtmlDialog::m_pBrowserApp
- AFXDHTML/CDHtmlDialog::m_spHtmlDoc
- AFXDHTML/CDHtmlDialog::m_strCurrentUrl
- AFXDHTML/CDHtmlDialog::m_szHtmlResID
dev_langs:
- C++
helpviewer_keywords:
- CDHtmlDialog class
ms.assetid: 3f941c85-87e1-4f0f-9cc5-ffee8498b312
caps.latest.revision: 23
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
ms.openlocfilehash: adf3664da1ecd1bdde9a1bd13e5b43ab7695e4d7
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cdhtmldialog-class"></a>CDHtmlDialog 類別
用來建立對話方塊使用 HTML，而不是實作其使用者介面對話方塊資源。  
  
## <a name="syntax"></a>語法  
  
```  
class CDHtmlDialog : public CDialog, public CDHtmlEventSink  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[CDHtmlDialog::CDHtmlDialog](#cdhtmldialog)|建構 CDHtmlDialog 物件。|  
|[CDHtmlDialog:: ~ CDHtmlDialog](#cdhtmldialog__~cdhtmldialog)|終結 CDHtmlDialog 物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CDHtmlDialog::CanAccessExternal](#canaccessexternal)|可覆寫，被稱為存取檢查，以查看是否已載入的頁面上的指令碼物件可以存取外部的控制項站台指派。 會檢查以確定分派是安全的指令碼，或是目前的區域是用來對指令碼是不安全的物件。|  
|[CDHtmlDialog::CreateControlSite](#createcontrolsite)|可覆寫用來建立裝載 WebBrowser 控制項在對話方塊上的控制項站台執行個體。|  
|[CDHtmlDialog::DDX_DHtml_AxControl](#ddx_dhtml_axcontrol)|HTML 網頁上的 ActiveX 控制項的屬性值的成員變數之間交換資料。|  
|[CDHtmlDialog::DDX_DHtml_CheckBox](#ddx_dhtml_checkbox)|HTML 網頁上的核取方塊的成員變數之間交換資料。|  
|[CDHtmlDialog::DDX_DHtml_ElementText](#ddx_dhtml_elementtext)|HTML 網頁上的任何 HTML 項目屬性的成員變數之間交換資料。|  
|[CDHtmlDialog::DDX_DHtml_Radio](#ddx_dhtml_radio)|成員變數，以及 HTML 網頁上的選項按鈕之間交換資料。|  
|[CDHtmlDialog::DDX_DHtml_SelectIndex](#ddx_dhtml_selectindex)|取得或設定 HTML 網頁上的清單方塊的索引。|  
|[CDHtmlDialog::DDX_DHtml_SelectString](#ddx_dhtml_selectstring)|取得或設定 HTML 網頁上的清單方塊項目 （根據目前的索引） 的顯示文字。|  
|[CDHtmlDialog::DDX_DHtml_SelectValue](#ddx_dhtml_selectvalue)|取得或設定 HTML 網頁上的清單方塊項目 （根據目前的索引） 的值。|  
|[CDHtmlDialog::DestroyModeless](#destroymodeless)|終結非強制回應對話方塊。|  
|[CDHtmlDialog::EnableModeless](#enablemodeless)|可讓非強制回應對話方塊。|  
|[CDHtmlDialog::FilterDataObject](#filterdataobject)|可讓篩選所裝載的瀏覽器建立剪貼簿資料物件 對話方塊。|  
|[CDHtmlDialog::GetControlDispatch](#getcontroldispatch)|擷取`IDispatch`介面上的 ActiveX 控制項嵌入 HTML 文件。|  
|[CDHtmlDialog::GetControlProperty](#getcontrolproperty)|擷取所要求的屬性指定的 ActiveX 控制項。|  
|[CDHtmlDialog::GetCurrentUrl](#getcurrenturl)|擷取與目前的文件，相關聯統一資源定位器 (URL)。|  
|[CDHtmlDialog::GetDHtmlDocument](#getdhtmldocument)|擷取目前載入的 HTML 文件上的 IHTMLDocument2 介面。|  
|[CDHtmlDialog::GetDropTarget](#getdroptarget)|它正做為置放目標以便提供替代對話方塊時，由內含的 WebBrowser 控制項呼叫[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)。|  
|[CDHtmlDialog::GetElement](#getelement)|取得 HTML 項目上的介面。|  
|[CDHtmlDialog::GetElementHtml](#getelementhtml)|擷取**innerHTML** HTML 項目的屬性。|  
|[CDHtmlDialog::GetElementInterface](#getelementinterface)|擷取要求的介面指標，從 HTML 項目。|  
|[CDHtmlDialog::GetElementProperty](#getelementproperty)|擷取的 HTML 項目屬性的值。|  
|[CDHtmlDialog::GetElementText](#getelementtext)|擷取**innerText** HTML 項目的屬性。|  
|[CDHtmlDialog::GetEvent](#getevent)|取得**IHTMLEventObj**目前事件物件的指標。|  
|[CDHtmlDialog::GetExternal](#getexternal)|取得主應用程式的`IDispatch`介面。|  
|[CDHtmlDialog::GetHostInfo](#gethostinfo)|擷取主機的 UI 功能。|  
|[CDHtmlDialog::GetOptionKeyPath](#getoptionkeypath)|擷取使用者喜好設定會儲存在其下的登錄機碼。|  
|[CDHtmlDialog::HideUI](#hideui)|隱藏主機的 UI。|  
|[CDHtmlDialog::IsExternalDispatchSafe](#isexternaldispatchsafe)|指出是否在主機`IDispatch`介面是可安全用於指令碼。|  
|[CDHtmlDialog::LoadFromResource](#loadfromresource)|載入 WebBrowser 控制項中指定的資源。|  
|[CDHtmlDialog::Navigate](#navigate)|巡覽至指定的 URL。|  
|[CDHtmlDialog::OnBeforeNavigate](#onbeforenavigate)|巡覽事件引發之前，由架構呼叫。|  
|[CDHtmlDialog::OnDocumentComplete](#ondocumentcomplete)|已到達文件時，通知應用程式架構呼叫`READYSTATE_COMPLETE`狀態。|  
|[CDHtmlDialog::OnDocWindowActivate](#ondocwindowactivate)|當文件視窗是啟用或停用時，由架構呼叫。|  
|[CDHtmlDialog::OnFrameWindowActivate](#onframewindowactivate)|框架視窗是啟用或停用時，由架構呼叫。|  
|[CDHtmlDialog::OnInitDialog](#oninitdialog)|呼叫以回應**WM_INITDIALOG**訊息。|  
|[CDHtmlDialog::OnNavigateComplete](#onnavigatecomplete)|巡覽事件完成後，由架構呼叫。|  
|[CDHtmlDialog::ResizeBorder](#resizeborder)|警示的物件，以便調整其框線空間。|  
|[CDHtmlDialog::SetControlProperty](#setcontrolproperty)|將 ActiveX 控制項的屬性設定為新值。|  
|[CDHtmlDialog::SetElementHtml](#setelementhtml)|設定**innerHTML** HTML 項目的屬性。|  
|[CDHtmlDialog::SetElementProperty](#setelementproperty)|設定 HTML 項目的屬性。|  
|[CDHtmlDialog::SetElementText](#setelementtext)|設定**innerText** HTML 項目的屬性。|  
|[CDHtmlDialog::SetExternalDispatch](#setexternaldispatch)|設定主機的`IDispatch`介面。|  
|[CDHtmlDialog::SetHostFlags](#sethostflags)|設定主機的 UI 旗標。|  
|[CDHtmlDialog::ShowContextMenu](#showcontextmenu)|顯示內容功能表時呼叫。|  
|[CDHtmlDialog::ShowUI](#showui)|顯示主機的 UI。|  
|[CDHtmlDialog::TranslateAccelerator](#translateaccelerator)|功能表快速鍵訊息處理的呼叫。|  
|[CDHtmlDialog::TranslateUrl](#translateurl)|呼叫以修改要載入的 URL。|  
|[CDHtmlDialog::UpdateUI](#updateui)|呼叫以通知主機命令狀態已變更。|  
  
### <a name="public-data-members"></a>公用資料成員  
  
|名稱|說明|  
|----------|-----------------|  
|[CDHtmlDialog::m_bUseHtmlTitle](#m_busehtmltitle)|指出是否要使用 HTML 文件的標題為對話方塊標題。|  
|[CDHtmlDialog::m_nHtmlResID](#m_nhtmlresid)|要顯示的資源識別碼的 HTML 資源。|  
|[CDHtmlDialog::m_pBrowserApp](#m_pbrowserapp)|Web 瀏覽器應用程式的指標。|  
|[CDHtmlDialog::m_spHtmlDoc](#m_sphtmldoc)|在 HTML 文件指標。|  
|[CDHtmlDialog::m_strCurrentUrl](#m_strcurrenturl)|目前的 URL。|  
|[CDHtmlDialog::m_szHtmlResID](#m_szhtmlresid)|版本字串的 HTML 資源識別碼。|  
  
## <a name="remarks"></a>備註  
 **CDHtmlDialog**可以載入的 HTML 中顯示的是 HTML 資源或 URL。  
  
 `CDHtmlDialog`可也進行資料交換與 HTML 控制項和處理 HTML 控制項中的事件，例如按一下按鈕。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDHtmlSinkHandlerBase2`  
  
 `CDHtmlSinkHandlerBase1`  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDHtmlSinkHandler`  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDHtmlEventSink`  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CDHtmlDialog`  
  
## <a name="requirements"></a>需求  
 **標頭︰** afxdhtml.h  
  
##  <a name="ddx_dhtml_helper_macros"></a>DDX_DHtml Helper 巨集  
 DDX_DHtml helper 巨集可讓您輕鬆存取常用的 HTML 網頁上的控制項屬性。  
  
### <a name="data-exchange-macros"></a>資料交換巨集  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementvalue)|設定或從選取的控制項擷取值的屬性。|  
|[DDX_DHtml_ElementInnerText](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnertext)|設定或擷取目前項目的開始和結束標記之間的文字。|  
|[DDX_DHtml_ElementInnerHtml](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_elementinnerhtml)|設定或擷取目前項目的開始和結束標記之間的 HTML。|  
|[DDX_DHtml_Anchor_Href](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_href)|設定或擷取目的地 URL 或錨點。|  
|[DDX_DHtml_Anchor_Target](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_anchor_target)|設定或擷取的目標視窗或框架。|  
|[DDX_DHtml_Img_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_img_src)|設定或擷取映像或文件中的視訊剪輯的名稱。|  
|[DDX_DHtml_Frame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_frame_src)|設定或擷取關聯框架的 URL。|  
|[DDX_DHtml_IFrame_Src](../../mfc/reference/ddx-dhtml-helper-macros.md#ddx_dhtml_iframe_src)|設定或擷取關聯框架的 URL。|  
  
##  <a name="canaccessexternal"></a>CDHtmlDialog::CanAccessExternal  
 可覆寫，被稱為存取檢查，以查看是否已載入的頁面上的指令碼物件可以存取外部的控制項站台指派。 會檢查以確定分派是安全的指令碼，或是目前的區域是用來對指令碼是不安全的物件。  
  
```  
virtual BOOL CanAccessExternal();
```  
  
### <a name="return-value"></a>傳回值  
 如果成功則為非零；否則為 0。  
  
##  <a name="cdhtmldialog"></a>CDHtmlDialog::CDHtmlDialog  
 建構資源型動態 HTML 對話方塊。  
  
```  
CDHtmlDialog();

 
CDHtmlDialog(
    LPCTSTR lpszTemplateName,  
    LPCTSTR szHtmlResID,  
    CWnd *pParentWnd = NULL);

 
CDHtmlDialog(
    UINT nIDTemplate,  
    UINT nHtmlResID = 0,  
    CWnd *pParentWnd = NULL);
```  
  
### <a name="parameters"></a>參數  
 `lpszTemplateName`  
 對話方塊範本資源的名稱以 null 結束字串。  
  
 `szHtmlResID`  
 以 null 結束的字串是 HTML 資源名稱。  
  
 `pParentWnd`  
 父系或擁有者的視窗物件的指標 (類型的[CWnd](../../mfc/reference/cwnd-class.md)) 對話方塊物件所屬。 如果是**NULL**，對話方塊物件的父視窗設為主要應用程式視窗。  
  
 `nIDTemplate`  
 包含對話方塊範本資源的 ID 編號。  
  
 `nHtmlResID`  
 包含 HTML 資源的 ID 編號。  
  
### <a name="remarks"></a>備註  
 第二個建構函式的形式提供透過範本名稱對話方塊資源的存取權。 第三個建構函式的形式提供的資源範本識別碼透過對話方塊資源的存取權。 通常，識別碼開始**IDD_**前置詞。  
  
##  <a name="_dtorcdhtmldialog"></a>CDHtmlDialog:: ~ CDHtmlDialog  
 終結 CDHtmlDialog 物件。  
  
```  
virtual ~CDHtmlDialog();
```  
  
### <a name="remarks"></a>備註  
 [Cwnd:: Destroywindow](../../mfc/reference/cwnd-class.md#destroywindow)成員函式必須用於摧毀所建立的非強制回應對話方塊[CDialog::Create](../../mfc/reference/cdialog-class.md#create)。  
  
##  <a name="createcontrolsite"></a>CDHtmlDialog::CreateControlSite  
 可覆寫用來建立裝載 WebBrowser 控制項在對話方塊上的控制項站台執行個體。  
  
```  
virtual BOOL CreateControlSite(
    COleControlContainer* pContainer,  
    COleControlSite** ppSite,  
    UINT /* nID */,  
    REFCLSID /* clsid */);
```  
  
### <a name="parameters"></a>參數  
 `pContainer`  
 指標[COleControlContainer](../../mfc/reference/colecontrolcontainer-class.md)物件  
  
 `ppSite`  
 指標的指標[COleControlSite](../../mfc/reference/colecontrolsite-class.md)。  
  
### <a name="return-value"></a>傳回值  
 如果成功則為非零；否則為 0。  
  
### <a name="remarks"></a>備註  
 您可以覆寫此成員函式，以傳回您自己的控制項站台類別的執行個體。  
  
##  <a name="ddx_dhtml_axcontrol"></a>CDHtmlDialog::DDX_DHtml_AxControl  
 HTML 網頁上的 ActiveX 控制項的屬性值的成員變數之間交換資料。  
  
```  
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    VARIANT& var);

 
void DDX_DHtml_AxControl(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    LPCTSTR szPropName,  
    VARIANT& var);
```  
  
### <a name="parameters"></a>參數  
 `pDX`  
 指標[CDataExchange](../../mfc/reference/cdataexchange-class.md)物件。  
  
 `szId`  
 ActiveX 控制項的 HTML 原始檔中的物件標記的 ID 參數的值。  
  
 `dispid`  
 您要交換資料之屬性的分派 ID。  
  
 `szPropName`  
 屬性的名稱。  
  
 `var`  
 型別的資料成員`VARIANT`， [COleVariant](../../mfc/reference/colevariant-class.md)，或[CComVariant](../../atl/reference/ccomvariant-class.md)，保存之交換所使用的 ActiveX 控制項屬性的值。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCHtmlHttp #&1;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_1.cpp)]  
  
##  <a name="ddx_dhtml_checkbox"></a>CDHtmlDialog::DDX_DHtml_CheckBox  
 HTML 網頁上的核取方塊的成員變數之間交換資料。  
  
```  
void DDX_DHtml_CheckBox(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    int& value);
```  
  
### <a name="parameters"></a>參數  
 `pDX`  
 指標[CDataExchange](../../mfc/reference/cdataexchange-class.md)物件。  
  
 `szId`  
 您指定 HTML 控制項的 ID 參數的值。  
  
 *value*  
 要交換的值。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCHtmlHttp #&2;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_2.cpp)]  
  
##  <a name="ddx_dhtml_elementtext"></a>CDHtmlDialog::DDX_DHtml_ElementText  
 HTML 網頁上的任何 HTML 項目屬性的成員變數之間交換資料。  
  
```  
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    CString& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    short& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    int& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    long& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    DWORD& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    float& value);

 
void DDX_DHtml_ElementText(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    DISPID dispid,  
    double& value);
```  
  
### <a name="parameters"></a>參數  
 `pDX`  
 指標[CDataExchange](../../mfc/reference/cdataexchange-class.md)物件。  
  
 `szId`  
 您指定 HTML 控制項的 ID 參數的值。  
  
 *dispid*  
 分派 ID，您要交換資料的 HTML 項目。  
  
 *value*  
 要交換的值。  
  
##  <a name="ddx_dhtml_radio"></a>CDHtmlDialog::DDX_DHtml_Radio  
 成員變數，以及 HTML 網頁上的選項按鈕之間交換資料。  
  
```  
void DDX_DHtml_Radio(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>參數  
 `pDX`  
 指標[CDataExchange](../../mfc/reference/cdataexchange-class.md)物件。  
  
 `szId`  
 您指定 HTML 控制項的 ID 參數的值。  
  
 *value*  
 要交換的值。  
  
##  <a name="ddx_dhtml_selectindex"></a>CDHtmlDialog::DDX_DHtml_SelectIndex  
 取得或設定 HTML 網頁上的清單方塊的索引。  
  
```  
void DDX_DHtml_SelectIndex(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    long& value);
```  
  
### <a name="parameters"></a>參數  
 `pDX`  
 指標[CDataExchange](../../mfc/reference/cdataexchange-class.md)物件。  
  
 `szId`  
 您指定 HTML 控制項的 id 參數的值。  
  
 *value*  
 要交換的值。  
  
##  <a name="ddx_dhtml_selectstring"></a>CDHtmlDialog::DDX_DHtml_SelectString  
 取得或設定 HTML 網頁上的清單方塊項目 （根據目前的索引） 的顯示文字。  
  
```  
void DDX_DHtml_SelectString(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>參數  
 `pDX`  
 指標[CDataExchange](../../mfc/reference/cdataexchange-class.md)物件。  
  
 `szId`  
 您指定 HTML 控制項的 ID 參數的值。  
  
 *value*  
 要交換的值。  
  
##  <a name="ddx_dhtml_selectvalue"></a>CDHtmlDialog::DDX_DHtml_SelectValue  
 取得或設定 HTML 網頁上的清單方塊項目 （根據目前的索引） 的值。  
  
```  
void DDX_DHtml_SelectValue(
    CDataExchange* pDX,  
    LPCTSTR szId,  
    CString& value);
```  
  
### <a name="parameters"></a>參數  
 `pDX`  
 指標[CDataExchange](../../mfc/reference/cdataexchange-class.md)物件。  
  
 `szId`  
 您指定 HTML 控制項的 ID 參數的值。  
  
 *value*  
 要交換的值。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCHtmlHttp #&3;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_3.cpp)]  
  
##  <a name="destroymodeless"></a>CDHtmlDialog::DestroyModeless  
 中斷連結從非強制回應對話方塊`CDHtmlDialog`物件，並終結物件。  
  
```  
void DestroyModeless();
```  
  
##  <a name="enablemodeless"></a>CDHtmlDialog::EnableModeless  
 可讓非強制回應對話方塊。  
  
```  
STDMETHOD(EnableModeless)(BOOL fEnable);
```  
  
### <a name="parameters"></a>參數  
 `fEnable`  
 請參閱`fEnable`中[IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::EnableModeless](https://msdn.microsoft.com/library/aa753253.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="filterdataobject"></a>CDHtmlDialog::FilterDataObject  
 可讓篩選所裝載的瀏覽器建立剪貼簿資料物件 對話方塊。  
  
```  
STDMETHOD(FilterDataObject)(
    IDataObject* pDO,  
    IDataObject** ppDORet);
```  
  
### <a name="parameters"></a>參數  
 `pDO`  
 請參閱`pDO`中[IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `ppDORet`  
 請參閱`ppDORet`中**IDocHostUIHandler::FilterDataObject**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**S_FALSE**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::FilterDataObject](https://msdn.microsoft.com/library/aa753254.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="getcontroldispatch"></a>CDHtmlDialog::GetControlDispatch  
 擷取`IDispatch`介面上的 ActiveX 控制項內嵌在 HTML 文件傳回[GetDHtmlDocument](#getdhtmldocument)。  
  
```  
HRESULT GetControlDispatch(
    LPCTSTR szId,  
    IDispatch** ppdisp);
```  
  
### <a name="parameters"></a>參數  
 `szId`  
 ActiveX 控制項的 HTML ID。  
  
 *ppdisp*  
 `IDispatch`控制項介面如果在網頁中找到。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
##  <a name="getcontrolproperty"></a>CDHtmlDialog::GetControlProperty  
 擷取所要求的屬性指定的 ActiveX 控制項。  
  
```  
VARIANT GetControlProperty(
    LPCTSTR szId,  
    LPCTSTR szPropName);

 
VARIANT GetControlProperty(
    LPCTSTR szId,  
    DISPID dispid);

 
VARIANT GetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>參數  
 `szId`  
 ActiveX 控制項的 HTML ID。  
  
 `szPropName`  
 目前使用者的預設地區設定中的屬性名稱。  
  
 `pdispControl`  
 `IDispatch` ActiveX 控制項的指標。  
  
 `dispid`  
 屬性的分派 ID。  
  
### <a name="return-value"></a>傳回值  
 如果控制項或屬性找不到包含要求的內容或空的 variant 變數。  
  
### <a name="remarks"></a>備註  
 多載會列出效率最差頂端到底部最有效率。  
  
##  <a name="getcurrenturl"></a>CDHtmlDialog::GetCurrentUrl  
 擷取與目前的文件，相關聯統一資源定位器 (URL)。  
  
```  
void GetCurrentUrl(CString& szUrl);
```  
  
### <a name="parameters"></a>參數  
 `szUrl`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md)物件，其中包含擷取的 URL。  
  
##  <a name="getdhtmldocument"></a>CDHtmlDialog::GetDHtmlDocument  
 擷取[IHTMLDocument2](https://msdn.microsoft.com/library/aa752574.aspx)介面上目前所載入的 HTML 文件。  
  
```  
HRESULT GetDHtmlDocument(IHTMLDocument2 **pphtmlDoc);
```  
  
### <a name="parameters"></a>參數  
 *\*\*pphtmlDoc*  
 指標的 HTML 文件的指標。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT`。 若成功，會傳回 `S_OK`。  
  
##  <a name="getdroptarget"></a>CDHtmlDialog::GetDropTarget  
 它正做為置放目標以便提供替代對話方塊時，由內含的 WebBrowser 控制項呼叫[IDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms679679)。  
  
```  
STDMETHOD(GetDropTarget)(
    IDropTarget* pDropTarget,  
    IDropTarget** ppDropTarget);
```  
  
### <a name="parameters"></a>參數  
 `pDropTarget`  
 請參閱`pDropTarget`中[IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `ppDropTarget`  
 請參閱`ppDropTarget`中**IDocHostUIHandler::GetDropTarget**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::GetDropTarget](https://msdn.microsoft.com/library/aa753255.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="getelement"></a>CDHtmlDialog::GetElement  
 傳回的介面上所指定的 HTML 項目`szElementId`。  
  
```  
HRESULT GetElement(
    LPCTSTR szElementId,  
    IDispatch** ppdisp,  
    BOOL* pbCollection = NULL);

 
HRESULT GetElement(
    LPCTSTR szElementId,  
    IHTMLElement** pphtmlElement);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
 *ppdisp*  
 `IDispatch`指標要求的項目或項目的集合。  
  
 *pbCollection*  
 A **BOOL**指出物件是否已由*ppdisp*的單一項目或項目的集合。  
  
 *pphtmlElement*  
 **樣式**要求項目的指標。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 使用第一個多載，如果您需要處理的情況中可能有一個以上的項目，並提供指定的識別碼。 若要了解是否傳回的介面指標集合或單一項目，您可以使用最後一個參數。 在集合上的介面指標時，您可以查詢**IHTMLElementCollection** ，並使用其**項目**屬性來參考依序數位置的項目。  
  
 如果有一個以上的項目具有相同識別碼在頁面中，將會失敗的第二個多載。  
  
##  <a name="getelementhtml"></a>CDHtmlDialog::GetElementHtml  
 擷取**innerHTML**屬性所識別之 HTML 項目`szElementId`。  
  
```  
BSTR GetElementHtml(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
### <a name="return-value"></a>傳回值  
 **InnerHTML**屬性所識別之 HTML 項目`szElementId`或**NULL**如果找不到項目。  
  
##  <a name="getelementinterface"></a>CDHtmlDialog::GetElementInterface  
 從所識別的 HTML 元素擷取要求的介面指標`szElementId`。  
  
```  
template <class Q> HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    Q** ppvObj);

 
HRESULT GetElementInterface(
    LPCTSTR szElementId,  
    REFIID riid,  
    void** ppvObj);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
 `ppvObj`  
 如果找到項目將會填入要求的介面指標的指標和查詢的位址就會成功。  
  
 `riid`  
 介面識別碼 (IID) 所要求介面。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCHtmlHttp #&4;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_4.cpp)]  
  
##  <a name="getelementproperty"></a>CDHtmlDialog::GetElementProperty  
 擷取所識別之屬性的值`dispid`所識別的 HTML 項目從`szElementId`。  
  
```  
VARIANT GetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
 `dispid`  
 屬性的分派 ID。  
  
### <a name="return-value"></a>傳回值  
 值的屬性，或是如果屬性或項目找不到一個空的 variant。  
  
##  <a name="getelementtext"></a>CDHtmlDialog::GetElementText  
 擷取**innerText**屬性所識別之 HTML 項目`szElementId`。  
  
```  
BSTR GetElementText(LPCTSTR szElementId);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
### <a name="return-value"></a>傳回值  
 **InnerText**屬性所識別之 HTML 項目`szElementId`或**NULL**如果無法找到的屬性或項目。  
  
##  <a name="getevent"></a>CDHtmlDialog::GetEvent  
 傳回**IHTMLEventObj**目前事件物件的指標。  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj);
```  
  
### <a name="parameters"></a>參數  
 `ppEventObj`  
 將會填入之指標的位址**IHTMLEventObj**介面指標。  
  
### <a name="return-value"></a>傳回值  
 標準 `HRESULT` 值。  
  
### <a name="remarks"></a>備註  
 只能從 DHTML 事件處理常式內呼叫此函式。  
  
##  <a name="getexternal"></a>CDHtmlDialog::GetExternal  
 取得主應用程式的`IDispatch`介面。  
  
```  
STDMETHOD(GetExternal)(IDispatch** ppDispatch);
```  
  
### <a name="parameters"></a>參數  
 *ppDispatch*  
 請參閱*ppDispatch*中[IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回`S_OK`成功或**E_NOTIMPL**失敗。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::GetExternal](https://msdn.microsoft.com/library/aa753256.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="gethostinfo"></a>CDHtmlDialog::GetHostInfo  
 擷取主機的 UI 功能。  
  
```  
STDMETHOD(GetHostInfo)(DOCHOSTUIINFO* pInfo);
```  
  
### <a name="parameters"></a>參數  
 `pInfo`  
 請參閱`pInfo`中[IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回 `S_OK`。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::GetHostInfo](https://msdn.microsoft.com/library/aa753257.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="getoptionkeypath"></a>CDHtmlDialog::GetOptionKeyPath  
 擷取使用者喜好設定會儲存在其下的登錄機碼。  
  
```  
STDMETHOD(GetOptionKeyPath)(
    LPOLESTR* pchKey,  
    DWORD dw);
```  
  
### <a name="parameters"></a>參數  
 `pchKey`  
 請參閱`pchKey`中[IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `dw`  
 請參閱`dw`中**IDocHostUIHandler::GetOptionKeyPath**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::GetOptionKeyPath](https://msdn.microsoft.com/library/aa753258.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="hideui"></a>CDHtmlDialog::HideUI  
 隱藏主機的 UI。  
  
```  
STDMETHOD(HideUI)(void);
```  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::HideUI](https://msdn.microsoft.com/library/aa753259.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="isexternaldispatchsafe"></a>CDHtmlDialog::IsExternalDispatchSafe  
 指出是否在主機`IDispatch`介面是可安全用於指令碼。  
  
```  
virtual BOOL IsExternalDispatchSafe();
```  
  
### <a name="return-value"></a>傳回值  
 傳回**FALSE**。  
  
##  <a name="loadfromresource"></a>CDHtmlDialog::LoadFromResource  
 載入 WebBrowser 控制項 DHTML 對話方塊中指定的資源。  
  
```  
BOOL LoadFromResource(LPCTSTR lpszResource);  
BOOL LoadFromResource(UINT nRes);
```  
  
### <a name="parameters"></a>參數  
 `lpszResource`  
 包含要載入的資源名稱的字串指標。  
  
 `nRes`  
 要載入的資源識別碼。  
  
### <a name="return-value"></a>傳回值  
 **TRUE**如果成功，否則**FALSE**。  
  
##  <a name="m_busehtmltitle"></a>CDHtmlDialog::m_bUseHtmlTitle  
 指出是否要使用 HTML 文件的標題為對話方塊標題。  
  
```  
BOOL m_bUseHtmlTitle;  
```  
  
### <a name="remarks"></a>備註  
 如果**m**_ **bUseHtmlTitle**是**true**、 對話方塊標題設定等於 HTML 文件的標題，否則會使用對話方塊資源中的標題。  
  
##  <a name="m_nhtmlresid"></a>CDHtmlDialog::m_nHtmlResID  
 要顯示的資源識別碼的 HTML 資源。  
  
```  
UINT m_nHtmlResID;  
```  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCHtmlHttp #&5;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_5.cpp)]  
  
##  <a name="m_pbrowserapp"></a>CDHtmlDialog::m_pBrowserApp  
 Web 瀏覽器應用程式的指標。  
  
```  
CComPtr <IWebBrowser2> m_pBrowserApp;  
```  
  
##  <a name="m_sphtmldoc"></a>CDHtmlDialog::m_spHtmlDoc  
 在 HTML 文件指標。  
  
```  
CComPtr<IHTMLDocument2> m_spHtmlDoc;  
```  
  
##  <a name="m_strcurrenturl"></a>CDHtmlDialog::m_strCurrentUrl  
 目前的 URL。  
  
```  
CString m_strCurrentUrl;  
```  
  
##  <a name="m_szhtmlresid"></a>CDHtmlDialog::m_szHtmlResID  
 版本字串的 HTML 資源識別碼。  
  
```  
LPTSTR m_szHtmlResID;  
```  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCHtmlHttp #&6;](../../mfc/reference/codesnippet/cpp/cdhtmldialog-class_6.cpp)]  
  
##  <a name="navigate"></a>CDHtmlDialog::Navigate  
 瀏覽至所指定的 URL 所識別的資源`lpszURL`。  
  
```  
void Navigate(
    LPCTSTR lpszURL,  
    DWORD dwFlags = 0,  
    LPCTSTR lpszTargetFrameName = NULL,  
    LPCTSTR lpszHeaders = NULL,  
    LPVOID lpvPostData = NULL,  
    DWORD dwPostDataLen = 0);
```  
  
### <a name="parameters"></a>參數  
 `lpszURL`  
 包含做為目標 URL 的字串指標。  
  
 `dwFlags`  
 指定是否要將資源新增至歷程記錄清單、 是否要快取讀取或寫入快取，以及是否要在新視窗中顯示的資源之變數的旗標。 變數可以是所定義之值的組合[BrowserNavConstants](https://msdn.microsoft.com/library/aa768360.aspx)列舉型別。  
  
 `lpszTargetFrameName`  
 包含要在其中顯示資源的框架名稱的字串指標。  
  
 `lpszHeaders`  
 指定要傳送至伺服器的 HTTP 標頭值的指標。 這些標頭會新增至預設的 Internet Explorer 標頭。 標頭可以指定這類資訊的伺服器，傳遞至伺服器或狀態碼的資料類型所需的動作。 如果 URL 不是 HTTP URL，則會忽略此參數。  
  
 `lpvPostData`  
 要傳送的 HTTP POST 交易的資料指標。 例如，POST 交易用來傳送 HTML 格式所收集的資料。 如果這個參數未指定任何張貼的資料，**瀏覽**發出 HTTP GET 的交易。 如果 URL 不是 HTTP URL，則會忽略此參數。  
  
 `dwPostDataLen`  
 傳送 HTTP POST 交易資料。 例如，POST 交易用來傳送 HTML 格式所收集的資料。 如果這個參數未指定任何張貼的資料，**瀏覽**發出 HTTP GET 的交易。 如果 URL 不是 HTTP URL，則會忽略此參數。  
  
##  <a name="onbeforenavigate"></a>CDHtmlDialog::OnBeforeNavigate  
 瀏覽發生之前引發事件的架構所呼叫。  
  
```  
virtual void OnBeforeNavigate(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>參數  
 `pDisp`  
 `IDispatch` 物件的指標。  
  
 `szUrl`  
 包含要巡覽至 URL 的字串指標。  
  
##  <a name="ondocumentcomplete"></a>CDHtmlDialog::OnDocumentComplete  
 已達成文件時，通知應用程式架構呼叫`READYSTATE_COMPLETE`狀態。  
  
```  
virtual void OnDocumentComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>參數  
 `pDisp`  
 `IDispatch` 物件的指標。  
  
 `szUrl`  
 包含巡覽至 URL 的字串指標。  
  
##  <a name="ondocwindowactivate"></a>CDHtmlDialog::OnDocWindowActivate  
 當文件視窗是啟用或停用時，由架構呼叫。  
  
```  
STDMETHOD(OnDocWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>參數  
 `fActivate`  
 請參閱`fActivate`中[IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作所[IDocHostUIHandler::OnDocWindowActivate](https://msdn.microsoft.com/library/aa753261.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="onframewindowactivate"></a>CDHtmlDialog::OnFrameWindowActivate  
 框架視窗是啟用或停用時，由架構呼叫。  
  
```  
STDMETHOD(OnFrameWindowActivate)(BOOL fActivate);
```  
  
### <a name="parameters"></a>參數  
 `fActivate`  
 請參閱`fActivate`中[IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::OnFrameWindowActivate](https://msdn.microsoft.com/library/aa753262.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="oninitdialog"></a>CDHtmlDialog::OnInitDialog  
 呼叫以回應**WM_INITDIALOG**訊息。  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>傳回值  
 預設實作會傳回**TRUE**。  
  
### <a name="remarks"></a>備註  
 此訊息會傳送到對話方塊期間**建立**， `CreateIndirect`，或`DoModal`呼叫，就會發生之前的對話方塊隨即出現。  
  
 如果您需要執行特殊處理初始化對話方塊時，覆寫此成員函式。 在覆寫的版本，先呼叫基底類別`OnInitDialog`但忽略它的傳回值。 您通常會傳回**TRUE**從您的覆寫的成員函式。  
  
 Windows 呼叫`OnInitDialog`函式透過 Mfc 程式庫廠商對話方塊通用標準的通用對話方塊中的程序，而不是透過訊息對應，因此您不需要的訊息對應項目為此成員函式。  
  
##  <a name="onnavigatecomplete"></a>CDHtmlDialog::OnNavigateComplete  
 瀏覽至指定的 URL 完成後，由架構呼叫。  
  
```  
virtual void OnNavigateComplete(
    LPDISPATCH pDisp,  
    LPCTSTR szUrl);
```  
  
### <a name="parameters"></a>參數  
 `pDisp`  
 `IDispatch` 物件的指標。  
  
 `szUrl`  
 包含巡覽至 URL 的字串指標。  
  
##  <a name="resizeborder"></a>CDHtmlDialog::ResizeBorder  
 警示的物件，以便調整其框線空間。  
  
```  
STDMETHOD(ResizeBorder)(
    LPCRECT prcBorder,  
    IOleInPlaceUIWindow* pUIWindow,  
    BOOL fRameWindow);
```  
  
### <a name="parameters"></a>參數  
 `prcBorder`  
 請參閱`prcBorder`中[IDocHostUIHandler::ResizeBorder](https://msdn.microsoft.com/library/aa753263.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pUIWindow`  
 請參閱`pUIWindow`中**IDocHostUIHandler::ResizeBorder**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `fFrameWindow`  
 請參閱*fFrameWindow*中**IDocHostUIHandler::ResizeBorder**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
##  <a name="setcontrolproperty"></a>CDHtmlDialog::SetControlProperty  
 將 ActiveX 控制項的屬性設定為新值。  
  
```  
void SetControlProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    IDispatch* pdispControl,  
    DISPID dispid,  
    VARIANT* pVar);

 
void SetControlProperty(
    LPCTSTR szElementId,  
    LPCTSTR szPropName,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 ActiveX 控制項的 HTML ID。  
  
 `dispid`  
 若要設定屬性的分派 ID。  
  
 *pVar*  
 指標**VARIANT**包含新的屬性值。  
  
 `pdispControl`  
 ActiveX 控制項的指標`IDispatch`介面。  
  
 `szPropName`  
 字串，包含要設定之屬性的名稱。  
  
##  <a name="setelementhtml"></a>CDHtmlDialog::SetElementHtml  
 設定**innerHTML** HTML 項目的屬性。  
  
```  
void SetElementHtml(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementHtml(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
 `bstrText`  
 新值**innerHTML**屬性。  
  
 `punkElem`  
 **IUnknown** HTML 項目的指標。  
  
##  <a name="setelementproperty"></a>CDHtmlDialog::SetElementProperty  
 設定 HTML 項目的屬性。  
  
```  
void SetElementProperty(
    LPCTSTR szElementId,  
    DISPID dispid,  
    VARIANT* pVar);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
 `dispid`  
 若要設定屬性的分派 ID。  
  
 *pVar*  
 屬性的新值。  
  
##  <a name="setelementtext"></a>CDHtmlDialog::SetElementText  
 設定**innerText** HTML 項目的屬性。  
  
```  
void SetElementText(
    LPCTSTR szElementId,  
    BSTR bstrText);

 
void SetElementText(
    IUnknown* punkElem,  
    BSTR bstrText);
```  
  
### <a name="parameters"></a>參數  
 `szElementId`  
 HTML 項目的識別碼。  
  
 `bstrText`  
 新值**innerText**屬性。  
  
 `punkElem`  
 **IUnknown** HTML 項目的指標。  
  
##  <a name="setexternaldispatch"></a>CDHtmlDialog::SetExternalDispatch  
 設定主機的`IDispatch`介面。  
  
```  
void SetExternalDispatch(IDispatch* pdispExternal);
```  
  
### <a name="parameters"></a>參數  
 *pdispExternal*  
 新`IDispatch`介面。  
  
##  <a name="sethostflags"></a>CDHtmlDialog::SetHostFlags  
 設定主應用程式 UI 的旗標。  
  
```  
void SetHostFlags(DWORD dwFlags);
```  
  
### <a name="parameters"></a>參數  
 `dwFlags`  
 可能的值，請參閱[DOCHOSTUIFLAG](https://msdn.microsoft.com/library/aa753277.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="showcontextmenu"></a>CDHtmlDialog::ShowContextMenu  
 顯示內容功能表時呼叫。  
  
```  
STDMETHOD(ShowContextMenu)(
    DWORD dwID,  
    POINT* ppt,  
    IUnknown* pcmdtReserved,  
    IDispatch* pdispReserved);
```  
  
### <a name="parameters"></a>參數  
 `dwID`  
 請參閱`dwID`中[IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `ppt`  
 請參閱`ppt`中**IDocHostUIHandler::ShowContextMenu**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pcmdtReserved`  
 請參閱`pcmdtReserved`中**IDocHostUIHandler::ShowContextMenu**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pdispReserved`  
 請參閱`pdispReserved`中**IDocHostUIHandler::ShowContextMenu**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**S_FALSE**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::ShowContextMenu](https://msdn.microsoft.com/library/aa753264.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="showui"></a>CDHtmlDialog::ShowUI  
 顯示主機的 UI。  
  
```  
STDMETHOD(ShowUI)(
    DWORD dwID,  
    IOleInPlaceActiveObject* pActiveObject,  
    IOleCommandTarget* pCommandTarget,  
    IOleInPlaceFrame* pFrame,  
    IOleInPlaceUIWindow* pDoc);
```  
  
### <a name="parameters"></a>參數  
 `dwID`  
 請參閱`dwID`中[IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pActiveObject`  
 請參閱*d pActiveObject*中**IDocHostUIHandler::ShowUI**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pCommandTarget`  
 請參閱`pCommandTarget`中**IDocHostUIHandler::ShowUI**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pFrame`  
 請參閱`pFrame`中**IDocHostUIHandler::ShowUI**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pDoc`  
 請參閱`pDoc`中**IDocHostUIHandler::ShowUI**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**S_FALSE**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::ShowUI](https://msdn.microsoft.com/library/aa753265.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="translateaccelerator"></a>CDHtmlDialog::TranslateAccelerator  
 功能表快速鍵訊息處理的呼叫。  
  
```  
STDMETHOD(TranslateAccelerator)(
    LPMSG lpMsg,  
    const GUID* pguidCmdGroup,  
    DWORD nCmdID);
```  
  
### <a name="parameters"></a>參數  
 `lpMsg`  
 請參閱`lpMsg`中[IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pguidCmdGroup`  
 請參閱`pguidCmdGroup`中**IDocHostUIHandler::TranslateAccelerator**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `nCmdID`  
 請參閱`nCmdID`中**IDocHostUIHandler::TranslateAccelerator**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**S_FALSE**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::TranslateAccelerator](https://msdn.microsoft.com/library/aa753266.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="translateurl"></a>CDHtmlDialog::TranslateUrl  
 呼叫以修改要載入的 URL。  
  
```  
STDMETHOD(TranslateUrl)(
    DWORD dwTranslate,  
    OLECHAR* pchURLIn,  
    OLECHAR** ppchURLOut);
```  
  
### <a name="parameters"></a>參數  
 `dwTranslate`  
 請參閱`dwTranslate`中[IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `pchURLIn`  
 請參閱`pchURLIn`中**IDocHostUIHandler::TranslateUrl**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
 `ppchURLOut`  
 請參閱`ppchURLOut`中**IDocHostUIHandler::TranslateUrl**中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
### <a name="return-value"></a>傳回值  
 傳回**S_FALSE**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::TranslateUrl](https://msdn.microsoft.com/library/aa753267.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
##  <a name="updateui"></a>CDHtmlDialog::UpdateUI  
 呼叫以通知主機命令狀態已變更。  
  
```  
STDMETHOD(UpdateUI)(void);
```  
  
### <a name="return-value"></a>傳回值  
 傳回**E_NOTIMPL**。  
  
### <a name="remarks"></a>備註  
 此成員函式是 CDHtmlDialog 的實作[IDocHostUIHandler::UpdateUI](https://msdn.microsoft.com/library/aa753268.aspx)所述，在[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
## <a name="see-also"></a>另請參閱  
 [MFC 範例 DHtmlExplore](../../visual-cpp-samples.md)   
 [DDX_DHtml Helper 巨集](#ddx_dhtml_helper_macros)   
 [階層架構圖表](../../mfc/hierarchy-chart.md)


