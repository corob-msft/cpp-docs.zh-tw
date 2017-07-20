---
title: "CHttpConnection 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHttpConnection
- AFXINET/CHttpConnection
- AFXINET/CHttpConnection::CHttpConnection
- AFXINET/CHttpConnection::OpenRequest
dev_langs:
- C++
helpviewer_keywords:
- servers, connecting to
- protocols, HTTP
- connecting to servers, HTTP servers
- Internet protocols, HTTP
- HTTP connections
- Internet protocols
- CHttpConnection class
- HTTP servers, connecting to
- connecting to servers
- Internet connections, HTTP
- connections [C++], HTTP
- Internet server, HTTP
ms.assetid: a402b662-c445-4988-800d-c8278551babe
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1b02a79cebbd73a05478887115646f0544f0a92d
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="chttpconnection-class"></a>CHttpConnection 類別
管理您與 HTTP 伺服器的連接。  
  
## <a name="syntax"></a>語法  
  
```  
class CHttpConnection : public CInternetConnection  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CHttpConnection::CHttpConnection](#chttpconnection)|建立 `CHttpConnection` 物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[Chttpconnection::](#openrequest)|開啟 HTTP 要求。|  
  
## <a name="remarks"></a>備註  
 HTTP 是其中一個 MFC WinInet 類別所實作的三種網際網路伺服器通訊協定。  
  
 類別`CHttpConnection`包含建構函式和一個成員函式， [OpenRequest](#openrequest)，來管理使用 HTTP 通訊協定與伺服器連接。  
  
 與 HTTP 伺服器通訊，您必須先建立的執行個體[CInternetSession](../../mfc/reference/cinternetsession-class.md)，然後再建立[CHttpConnection](#_mfc_chttpconnection)物件。 絕對不要建立`CHttpConnection`直接物件; 而是呼叫[Gethttpconnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)，這樣就可以建立`CHttpConnection`物件，並傳回的指標。  
  
 若要深入了解如何`CHttpConnection`運作方式與其他 MFC 網際網路類別，請參閱文章[網際網路程式設計 WinInet](../../mfc/win32-internet-extensions-wininet.md)。 如需有關連接到伺服器使用其他兩個支援的網際網路通訊協定、 gopher 和 FTP，請參閱類別[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)和[CFtpConnection](../../mfc/reference/cftpconnection-class.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)  
  
 `CHttpConnection`  
  
## <a name="requirements"></a>需求  
 **標頭︰** afxinet.h  
  
##  <a name="chttpconnection"></a>CHttpConnection::CHttpConnection  
 此成員函式呼叫來建構`CHttpConnection`物件。  
  
```  
CHttpConnection(
    CInternetSession* pSession,  
    HINTERNET hConnected,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);

 
CHttpConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    DWORD dwFlags,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    LPCTSTR pstrUserName = NULL,  
    LPCTSTR pstrPassword = NULL,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>參數  
 `pSession`  
 指標[CInternetSession](../../mfc/reference/cinternetsession-class.md)物件。  
  
 `hConnected`  
 連上網際網路控制代碼。  
  
 `pstrServer`  
 包含伺服器名稱的字串指標。  
  
 `dwContext`  
 內容識別碼`CInternetConnection`物件。 請參閱**備註**如需詳細資訊`dwContext`。  
  
 `nPort`  
 識別此連線的網際網路連接埠的數字。  
  
 `pstrUserName`  
 以 null 終止的字串，指定使用者登入名稱的指標。 如果**NULL**，預設值是匿名的。  
  
 `pstrPassword`  
 以 null 終止的字串，指定要用來登入密碼指標。 如果兩個`pstrPassword`和`pstrUserName`是**NULL**，預設匿名密碼是使用者的電子郵件名稱。 如果`pstrPassword`是**NULL** （或空字串），但`pstrUserName`不**NULL**，使用空白密碼。 下表說明的四個可能的設定行為`pstrUserName`和`pstrPassword`:  
  
|`pstrUserName`|`pstrPassword`|傳送至 FTP 伺服器的使用者名稱|傳送至 FTP 伺服器的密碼|  
|--------------------|--------------------|---------------------------------|---------------------------------|  
|**NULL**或 「 」|**NULL**或 「 」|「 匿名 」|使用者的電子郵件名稱|  
|非- **NULL**字串|**NULL**或 「 」|`pstrUserName`|" "|  
|**NULL**非**NULL**字串|**錯誤**|**錯誤**||  
|非- **NULL**字串|非- **NULL**字串|`pstrUserName`|`pstrPassword`|  
  
 `dwFlags`  
 任何組合**INTERNET_ FLAG_\* **旗標。 請參閱表格**備註**區段[chttpconnection::](#openrequest)的說明`dwFlags`值。  
  
### <a name="remarks"></a>備註  
 絕對不要建立`CHttpConnection`直接。 相反地，您建立物件呼叫[Gethttpconnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)。  
  
##  <a name="openrequest"></a>Chttpconnection::  
 呼叫此成員函式，以開啟 HTTP 連接。  
  
```  
CHttpFile* OpenRequest(
    LPCTSTR pstrVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);

 
CHttpFile* OpenRequest(
    int nVerb,  
    LPCTSTR pstrObjectName,  
    LPCTSTR pstrReferer = NULL,  
    DWORD_PTR dwContext = 1,  
    LPCTSTR* ppstrAcceptTypes = NULL,  
    LPCTSTR pstrVersion = NULL,  
    DWORD dwFlags = INTERNET_FLAG_EXISTING_CONNECT);
```  
  
### <a name="parameters"></a>參數  
 `pstrVerb`  
 包含在要求中使用的動詞命令的字串指標。 如果`NULL`，使用 「 取得 」。  
  
 `pstrObjectName`  
 包含指定的動詞命令的目標物件的字串指標。 這通常是檔名、 可執行模組或搜尋規範。  
  
 `pstrReferer`  
 指定的文件的位址 (URL) 字串的指標中要求的 URL ( `pstrObjectName`) 取得。 如果`NULL`，不指定任何 HTTP 標頭。  
  
 `dwContext`  
 內容識別碼`OpenRequest`作業。 請參閱 < 備註 > 一節，如需詳細資訊，關於`dwContext`。  
  
 `ppstrAcceptTypes`  
 之 null 終端陣列的指標`LPCTSTR`用戶端接受字串，表示內容類型的指標。 如果`ppstrAcceptTypes`是`NULL`，伺服器解譯用戶端只接受類型的文件 「 text / *"（也就是唯一的文字文件並不圖片或其他二進位檔案）。 內容類型相當於 CGI 變數 CONTENT_TYPE，識別已連接資訊，例如 HTTP POST 和 PUT 的查詢的資料類型。  
  
 `pstrVersion`  
 定義的 HTTP 版本字串的指標。 如果`NULL`，會使用 「 HTTP/1.0 」。  
  
 `dwFlags`  
 INTERNET_ FLAG_ * 旗標的任何組合。 請參閱 < 備註 > 一節說明可能的`dwFlags`值。  
  
 `nVerb`  
 HTTP 要求類型相關聯的數字。 可以是下列其中一項：  
  
|HTTP 要求類型|`nVerb` 值|  
|-----------------------|-------------------|  
|`HTTP_VERB_POST`|0|  
|`HTTP_VERB_GET`|1|  
|`HTTP_VERB_HEAD`|2|  
|`HTTP_VERB_PUT`|3|  
|`HTTP_VERB_LINK`|4|  
|`HTTP_VERB_DELETE`|5|  
|`HTTP_VERB_UNLINK`|6|  
  
### <a name="return-value"></a>傳回值  
 指標[CHttpFile](../../mfc/reference/chttpfile-class.md)要求物件。  
  
### <a name="remarks"></a>備註  
 `dwFlags` 可以是下列其中一項：  
  
|網際網路旗標|說明|  
|-------------------|-----------------|  
|`INTERNET_FLAG_RELOAD`|從原始伺服器，而不是從快取，會強制下載要求的檔案、 物件或目錄清單。|  
|`INTERNET_FLAG_DONT_CACHE`|不會新增至快取傳回的實體。|  
|`INTERNET_FLAG_MAKE_PERSISTENT`|新增至快取傳回的實體，做為持續性的實體。 這表示，標準快取清除、 一致性檢查，或回收無法移除此項目從快取。|  
|`INTERNET_FLAG_SECURE`|會使用安全的交易語意。 這會轉譯為使用 SSL/百分比，才有意義的 HTTP 要求|  
|`INTERNET_FLAG_NO_AUTO_REDIRECT`|僅適用於 HTTP、 指定的重新導向應該不會自動處理在[CHttpFile::SendRequest](../../mfc/reference/chttpfile-class.md#sendrequest)。|  
  
 覆寫`dwContext`預設將內容識別碼設定為您選擇的值。 內容識別碼是與這個特定作業的相關聯`CHttpConnection`所建立的物件及其[CInternetSession](../../mfc/reference/cinternetsession-class.md)物件。 若要傳回的值[CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)來提供與識別此作業的狀態。 請參閱文章[網際網路第一個步驟︰ WinInet](../../mfc/wininet-basics.md)如需有關內容識別碼。  
  
 此函式可能會擲回例外狀況。  
  
## <a name="see-also"></a>另請參閱  
 [CInternetConnection 類別](../../mfc/reference/cinternetconnection-class.md)   
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [CInternetConnection 類別](../../mfc/reference/cinternetconnection-class.md)   
 [CHttpFile 類別](../../mfc/reference/chttpfile-class.md)
