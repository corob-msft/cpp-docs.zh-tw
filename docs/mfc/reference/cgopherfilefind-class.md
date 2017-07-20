---
title: "CGopherFileFind 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFileFind
- AFXINET/CGopherFileFind
- AFXINET/CGopherFileFind::CGopherFileFind
- AFXINET/CGopherFileFind::FindFile
- AFXINET/CGopherFileFind::FindNextFile
- AFXINET/CGopherFileFind::GetCreationTime
- AFXINET/CGopherFileFind::GetLastAccessTime
- AFXINET/CGopherFileFind::GetLastWriteTime
- AFXINET/CGopherFileFind::GetLength
- AFXINET/CGopherFileFind::GetLocator
- AFXINET/CGopherFileFind::GetScreenName
- AFXINET/CGopherFileFind::IsDots
dev_langs:
- C++
helpviewer_keywords:
- CGopherFileFind class
- file searches [C++]
ms.assetid: 8465a979-6323-496d-ab4b-e81383fb999d
caps.latest.revision: 21
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
ms.openlocfilehash: 93f30e83369ad1bff7222f26d0782eed11e73f66
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherfilefind-class"></a>CGopherFileFind 類別
協助網際網路檔案搜尋 Gopher 伺服器。  
  
> [!NOTE]
>  類別`CGopherConnection`， `CGopherFile`， `CGopherFileFind`，`CGopherLocator`和其成員已被取代，因為無法在 Windows XP 平台上運作，但它們會繼續在舊版平台上運作。  
  
## <a name="syntax"></a>語法  
  
```  
class CGopherFileFind : public CFileFind  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CGopherFileFind::CGopherFileFind](#cgopherfilefind)|建構 `CGopherFileFind` 物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[CGopherFileFind::FindFile](#findfile)|尋找在 gopher 伺服器上的檔案。|  
|[CGopherFileFind::FindNextFile](#findnextfile)|繼續從先前呼叫該檔案[FindFile](#findfile)。|  
|[CGopherFileFind::GetCreationTime](#getcreationtime)|取得指定的檔案建立的時間。|  
|[CGopherFileFind::GetLastAccessTime](#getlastaccesstime)|取得指定的檔案上次被存取的時間。|  
|[CGopherFileFind::GetLastWriteTime](#getlastwritetime)|取得指定的檔案上次被寫入的時間。|  
|[CGopherFileFind::GetLength](#getlength)|取得找到的檔案，以位元組為單位的長度。|  
|[CGopherFileFind::GetLocator](#getlocator)|取得`CGopherLocator`物件。|  
|[CGopherFileFind::GetScreenName](#getscreenname)|取得 gopher 螢幕的名稱。|  
|[CGopherFileFind::IsDots](#isdots)|測試目前的目錄與父目錄資料標記逐一查看檔案時。|  
  
## <a name="remarks"></a>備註  
 `CGopherFileFind`包含成員函式開始搜尋，找出檔案，並傳回檔案的 URL。  
  
 設計的網際網路和搜尋的本機檔案包含其他 MFC 類別[CFtpFileFind](../../mfc/reference/cftpfilefind-class.md)和[CFileFind](../../mfc/reference/cfilefind-class.md)。 搭配`CGopherFileFind`，這些類別提供順暢的機制，讓使用者可用來尋找特定檔案，不論伺服器通訊協定、 檔案類型或位置 （本機電腦或遠端伺服器。）請注意，搜尋在 HTTP 伺服器上，HTTP 不支援搜尋所需的檔案操作作業，因為沒有 MFC 類別。  
  
> [!NOTE]
> `CGopherFileFind`不支援下列成員函式，其基底類別[CFileFind](../../mfc/reference/cfilefind-class.md):  
  
- [GetRoot](../../mfc/reference/cfilefind-class.md#getroot)  
  
- [GetFileName](../../mfc/reference/cfilefind-class.md#getfilename)  
  
- [GetFilePath](../../mfc/reference/cfilefind-class.md#getfilepath)  
  
- [GetFileTitle](../../mfc/reference/cfilefind-class.md#getfiletitle)  
  
- [GetFileURL](../../mfc/reference/cfilefind-class.md#getfileurl)  
  
 此外，當搭配`CGopherFileFind`、`CFileFind`成員函式[IsDots](../../mfc/reference/cfilefind-class.md#isdots)總是**FALSE**。  
  
 如需有關如何使用`CGopherFileFind`和其他 WinInet 類別，請參閱文章[網際網路程式設計 WinInet](../../mfc/win32-internet-extensions-wininet.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFileFind](../../mfc/reference/cfilefind-class.md)  
  
 `CGopherFileFind`  
  
## <a name="requirements"></a>需求  
 **標頭︰** afxinet.h  
  
##  <a name="cgopherfilefind"></a>CGopherFileFind::CGopherFileFind  
 此成員函式呼叫來建構`CGopherFileFind`物件。  
  
```  
explicit CGopherFileFind(
    CGopherConnection* pConnection,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>參數  
 `pConnection`  
 指標[CGopherConnection](../../mfc/reference/cgopherconnection-class.md)物件。  
  
 `dwContext`  
 作業的內容識別碼。 請參閱**備註**如需詳細資訊`dwContext`。  
  
### <a name="remarks"></a>備註  
 預設值為`dwContext`傳送到 mfc`CGopherFileFind`物件從[CInternetSession](../../mfc/reference/cinternetsession-class.md)物件建立`CGopherFileFind`物件。 當您建構`CGopherFileFind`物件時，您可以覆寫預設值，將內容識別碼設定為您選擇的值。 內容識別碼傳回給[CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)來提供其所識別的物件上的狀態。 請參閱文章[網際網路第一個步驟︰ WinInet](../../mfc/wininet-basics.md)如需有關內容識別碼。  
  
##  <a name="findfile"></a>CGopherFileFind::FindFile  
 呼叫此成員函式，以尋找 gopher 檔案。  
  
```  
virtual BOOL FindFile(
    CGopherLocator& refLocator,  
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);

 
virtual BOOL FindFile(
    LPCTSTR pstrString,  
    DWORD dwFlags = INTERNET_FLAG_RELOAD);
```  
  
### <a name="parameters"></a>參數  
 `refLocator`  
 參考[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)物件。  
  
 *pstrString*  
 包含檔案名稱的字串指標。  
  
 `dwFlags`  
 描述如何處理此工作階段旗標。 有效的旗標如下︰  
  
-   INTERNET_FLAG_RELOAD 從遠端伺服器取得的資料，即使在本機快取。  
  
-   在本機或所有閘道，請 INTERNET_FLAG_DONT_CACHE 不要快取資料。  
  
-   INTERNET_FLAG_SECURE 要求使用安全通訊端層或 PCT 網路上的安全交易 這個旗標適用於只有 HTTP 要求。  
  
-   INTERNET_FLAG_USE_EXISTING 如果可能的話，重複使用現有的連接到伺服器有新**FindFile**要求，而非建立新的工作階段，針對每個要求。  
  
### <a name="return-value"></a>傳回值  
 如果成功則為非零；否則為 0。 若要取得擴充的錯誤資訊，呼叫 Win32 函式[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)。  
  
### <a name="remarks"></a>備註  
 在呼叫**FindFile**若要擷取的第一個 gopher 物件，您可以呼叫[FindNextFile](#findnextfile)來擷取後續 gopher 檔案。  
  
##  <a name="findnextfile"></a>CGopherFileFind::FindNextFile  
 呼叫此成員函式，繼續呼叫開始檔案搜尋[CGopherFileFind::FindFile](#findfile)。  
  
```  
virtual BOOL FindNextFile();
```  
  
### <a name="return-value"></a>傳回值  
 非零，如果有多個檔案。如果找到該檔案的目錄中的最後一個，或發生錯誤，則為零。 若要取得擴充的錯誤資訊，呼叫 Win32 函式[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)。 如果找到該檔案的目錄中的最後一個檔案，或如果沒有相符的檔案就可以找到，`GetLastError`函式會傳回 ERROR_NO_MORE_FILES。  
  
##  <a name="getcreationtime"></a>CGopherFileFind::GetCreationTime  
 取得目前檔案的建立時間。  
  
```  
virtual BOOL GetCreationTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetCreationTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>參數  
 `pTimeStamp`  
 指標[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)結構，其中包含的檔案所建立的時間。  
  
 `refTime`  
 參考[CTime](../../atl-mfc-shared/reference/ctime-class.md)物件。  
  
### <a name="return-value"></a>傳回值  
 如果成功則為非零0，如果不成功。 `GetCreationTime`只會傳回 0 [FindNextFile](#findnextfile)永遠不會呼叫這個`CGopherFileFind`物件。  
  
### <a name="remarks"></a>備註  
 您必須呼叫[FindNextFile](#findnextfile)至少一次，才能呼叫`GetCreationTime`。  
  
> [!NOTE]
>  並非所有的檔案系統會使用相同的語意來實作此函數所傳回的時間戳記。 此函式可能會傳回相同的值，如果基礎檔案系統或伺服器不支援保留時間屬性，其他的時間戳記函式所傳回。 請參閱[Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)時間格式的相關資訊的結構。 在某些作業系統上傳回的時間是區域的本機電腦已為檔案所在的時間。 請參閱 Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API，如需詳細資訊。  
  
##  <a name="getlastaccesstime"></a>CGopherFileFind::GetLastAccessTime  
 取得指定的檔案上次被存取的時間。  
  
```  
virtual BOOL GetLastAccessTime(CTime& refTime) const;  
virtual BOOL GetLastAccessTime(FILETIME* pTimeStamp) const;  
```  
  
### <a name="parameters"></a>參數  
 `refTime`  
 參考[CTime](../../atl-mfc-shared/reference/ctime-class.md)物件。  
  
 `pTimeStamp`  
 指標[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)結構，其中包含檔案上次被存取的時間。  
  
### <a name="return-value"></a>傳回值  
 如果成功則為非零0，如果不成功。 `GetLastAccessTime`只會傳回 0 [FindNextFile](#findnextfile)永遠不會呼叫這個`CGopherFileFind`物件。  
  
### <a name="remarks"></a>備註  
 您必須呼叫[FindNextFile](#findnextfile)至少一次，才能呼叫`GetLastAccessTime`。  
  
> [!NOTE]
>  並非所有的檔案系統會使用相同的語意來實作此函數所傳回的時間戳記。 此函式可能會傳回相同的值，如果基礎檔案系統或伺服器不支援保留時間屬性，其他的時間戳記函式所傳回。 請參閱[Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)時間格式的相關資訊的結構。 在某些作業系統上傳回的時間是區域的本機電腦已為檔案所在的時間。 請參閱 Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API，如需詳細資訊。  
  
##  <a name="getlastwritetime"></a>CGopherFileFind::GetLastWriteTime  
 取得上次變更檔案的時間。  
  
```  
virtual BOOL GetLastWriteTime(FILETIME* pTimeStamp) const;  
virtual BOOL GetLastWriteTime(CTime& refTime) const;  
```  
  
### <a name="parameters"></a>參數  
 `pTimeStamp`  
 指標[FILETIME](http://msdn.microsoft.com/library/windows/desktop/ms724284)結構，其中包含檔案上次被寫入的時間。  
  
 `refTime`  
 參考[CTime](../../atl-mfc-shared/reference/ctime-class.md)物件。  
  
### <a name="return-value"></a>傳回值  
 如果成功則為非零0，如果不成功。 `GetLastWriteTime`只會傳回 0 [FindNextFile](#findnextfile)永遠不會呼叫這個`CGopherFileFind`物件。  
  
### <a name="remarks"></a>備註  
 您必須呼叫[FindNextFile](#findnextfile)至少一次，才能呼叫`GetLastWriteTime`。  
  
> [!NOTE]
>  並非所有的檔案系統會使用相同的語意來實作此函數所傳回的時間戳記。 此函式可能會傳回相同的值，如果基礎檔案系統或伺服器不支援保留時間屬性，其他的時間戳記函式所傳回。 請參閱[Win32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)時間格式的相關資訊的結構。 在某些作業系統上傳回的時間是區域的本機電腦已為檔案所在的時間。 請參閱 Win32 [FileTimeToLocalFileTime](http://msdn.microsoft.com/library/windows/desktop/ms724277) API，如需詳細資訊。  
  
##  <a name="getlength"></a>CGopherFileFind::GetLength  
 呼叫此成員函式，取得長度，以位元組為單位找到的檔案。  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
### <a name="return-value"></a>傳回值  
 找到檔案的長度，單位為位元組。  
  
### <a name="remarks"></a>備註  
 `GetLength`使用 Win32 結構[WIN32_FIND_DATA](http://msdn.microsoft.com/library/windows/desktop/aa365740)取得檔案大小的值以位元組為單位。  
  
> [!NOTE]
>  從 MFC 7.0`GetLength`支援 64 位元整數型別。 與這個較新版本的程式庫建置的先前現有程式碼可能會導致截斷警告。  
  
### <a name="example"></a>範例  
  請參閱範例[CFile::GetLength](../../mfc/reference/cfile-class.md#getlength) （基底類別實作）。  
  
##  <a name="getlocator"></a>CGopherFileFind::GetLocator  
 呼叫此成員函式可取得[CGopherLocator](../../mfc/reference/cgopherlocator-class.md)物件[FindFile](#findfile)用來尋找 gopher 檔案。  
  
```  
CGopherLocator GetLocator() const;  
```  
  
### <a name="return-value"></a>傳回值  
 `CGopherLocator` 物件。  
  
##  <a name="getscreenname"></a>CGopherFileFind::GetScreenName  
 呼叫此成員函式，以取得 gopher 螢幕的名稱。  
  
```  
CString GetScreenName() const;  
```  
  
### <a name="return-value"></a>傳回值  
 Gopher 螢幕的名稱。  
  
##  <a name="isdots"></a>CGopherFileFind::IsDots  
 測試目前的目錄與父目錄資料標記逐一查看檔案時。  
  
```  
virtual BOOL IsDots() const;  
```  
  
### <a name="return-value"></a>傳回值  
 非零，如果找到的檔案名稱 」。 「 或 」...」，這表示找到的檔案為實際的目錄。 否則為 0。  
  
### <a name="remarks"></a>備註  
 您必須呼叫[FindNextFile](#findnextfile)至少一次，才能呼叫`IsDots`。  
  
## <a name="see-also"></a>另請參閱  
 [CFileFind 類別](../../mfc/reference/cfilefind-class.md)   
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [CFtpFileFind 類別](../../mfc/reference/cftpfilefind-class.md)   
 [CFileFind 類別](../../mfc/reference/cfilefind-class.md)   
 [CInternetFile 類別](../../mfc/reference/cinternetfile-class.md)   
 [CGopherFile 類別](../../mfc/reference/cgopherfile-class.md)   
 [CHttpFile 類別](../../mfc/reference/chttpfile-class.md)
