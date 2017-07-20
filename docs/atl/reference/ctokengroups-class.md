---
title: "CTokenGroups 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
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
ms.openlocfilehash: 41b93e1c0a2e55013e280023a7f47610d38ddc10
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="ctokengroups-class"></a>CTokenGroups 類別
這個類別是包裝函式**TOKEN_GROUPS**結構。  
  
> [!IMPORTANT]
>  這個類別及其成員不能在 Windows 執行階段中執行的應用程式。  
  
## <a name="syntax"></a>語法  
  
```
class CTokenGroups
```  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CTokenGroups::CTokenGroups](#ctokengroups)|建構函式。|  
|[CTokenGroups:: ~ CTokenGroups](#dtor)|解構函式。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[CTokenGroups::Add](#add)|新增`CSid`或現有的**TOKEN_GROUPS**結構以`CTokenGroups`物件。|  
|[CTokenGroups::Delete](#delete)|刪除`CSid`和其相關聯的屬性，從`CTokenGroups`物件。|  
|[CTokenGroups::DeleteAll](#deleteall)|刪除所有`CSid`物件和其相關聯的屬性，從`CTokenGroups`物件。|  
|[CTokenGroups::GetCount](#getcount)|傳回的數字`CSid`物件和相關聯的屬性中包含**CTokenGroups**物件。|  
|[CTokenGroups::GetLength](#getlength)|傳回的大小`CTokenGroups`物件。|  
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|擷取的指標**TOKEN_GROUPS**結構。|  
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|擷取`CSid`物件和屬性屬於`CTokenGroups`物件。|  
|[CTokenGroups::LookupSid](#lookupsid)|擷取相關聯的屬性`CSid`物件。|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|描述|  
|----------|-----------------|  
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|轉換 （cast)`CTokenGroups`物件的指標**TOKEN_GROUPS**結構。|  
|[CTokenGroups::operator =](#operator_eq)|指派運算子。|  
  
## <a name="remarks"></a>備註  
 [存取權杖](http://msdn.microsoft.com/library/windows/desktop/aa374909)是一個物件，描述處理序或執行緒的安全性內容，並配置給每位使用者登入 Windows NT 或 Windows 2000 的系統。  
  
 **CTokenGroups**類別是包裝函式[TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)結構，包含存取權杖中的群組安全性識別碼 (Sid) 相關資訊。  
  
 在 Windows 中的存取控制模型的簡介，請參閱[存取控制](http://msdn.microsoft.com/library/windows/desktop/aa374860)中[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]。  
  
## <a name="requirements"></a>需求  
 **標頭︰** atlsecurity.h  
  
##  <a name="add"></a>CTokenGroups::Add  
 新增`CSid`或現有的**TOKEN_GROUPS**結構以`CTokenGroups`物件。  
  
```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );  
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```  
  
### <a name="parameters"></a>參數  
 `rSid`  
 A [CSid](../../atl/reference/csid-class.md)物件。  
  
 `dwAttributes`  
 與相關聯的屬性`CSid`物件。  
  
 *rTokenGroups*  
 A [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)結構。  
  
### <a name="remarks"></a>備註  
 這些方法會加入一個或多個`CSid`物件和其相關聯的屬性，以`CTokenGroups`物件。  
  
##  <a name="ctokengroups"></a>CTokenGroups::CTokenGroups  
 建構函式。  
  
```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );  
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```  
  
### <a name="parameters"></a>參數  
 `rhs`  
 `CTokenGroups`物件或[TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)結構，用來建構`CTokenGroups`物件。  
  
### <a name="remarks"></a>備註  
 `CTokenGroups`物件可以選擇性地建立使用**TOKEN_GROUPS**結構或先前定義`CTokenGroups`物件。  
  
##  <a name="dtor"></a>CTokenGroups:: ~ CTokenGroups  
 解構函式。  
  
```
virtual ~CTokenGroups() throw();
```  
  
### <a name="remarks"></a>備註  
 解構函式會釋放所有配置的資源。  
  
##  <a name="delete"></a>CTokenGroups::Delete  
 刪除`CSid`和其相關聯的屬性，從`CTokenGroups`物件。  
  
```
bool Delete(const CSid& rSid) throw();
```  
  
### <a name="parameters"></a>參數  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md)的安全性識別碼 (SID) 和屬性應該要移除的物件。  
  
### <a name="return-value"></a>傳回值  
 傳回 true 如果`CSid`移除時，false 否則。  
  
##  <a name="deleteall"></a>CTokenGroups::DeleteAll  
 刪除所有`CSid`物件和其相關聯的屬性，從`CTokenGroups`物件。  
  
```
void DeleteAll() throw();
```  
  
##  <a name="getcount"></a>CTokenGroups::GetCount  
 傳回的數字`CSid`物件中包含`CTokenGroups`。  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>傳回值  
 傳回的數字[CSid](../../atl/reference/csid-class.md)物件和關聯的屬性中包含`CTokenGroups`物件。  
  
##  <a name="getlength"></a>CTokenGroups::GetLength  
 傳回的大小**CTokenGroup**物件。  
  
```
UINT GetLength() const throw();
```  
  
### <a name="remarks"></a>備註  
 傳回的大小總計**CTokenGroup**物件，以位元組為單位。  
  
##  <a name="getptoken_groups"></a>CTokenGroups::GetPTOKEN_GROUPS  
 擷取的指標**TOKEN_GROUPS**結構。  
  
```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```  
  
### <a name="return-value"></a>傳回值  
 擷取的指標[TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)結構屬於`CTokenGroups`存取權杖的物件。  
  
##  <a name="getsidsandattributes"></a>CTokenGroups::GetSidsAndAttributes  
 擷取`CSid`物件及 （選擇性） 屬性屬於`CTokenGroups`物件。  
  
```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>參數  
 `pSids`  
 陣列的指標[CSid](../../atl/reference/csid-class.md)物件。  
  
 `pAttributes`  
 Dword 的陣列指標。 如果這個參數是省略，則為 NULL，不會擷取屬性。  
  
### <a name="remarks"></a>備註  
 這個方法會列舉所有`CSid`物件中包含`CTokenGroups`物件，並將它們以及 （選擇性） 的屬性旗標放入陣列物件。  
  
##  <a name="lookupsid"></a>CTokenGroups::LookupSid  
 擷取相關聯的屬性`CSid`物件。  
  
```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```  
  
### <a name="parameters"></a>參數  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md)物件。  
  
 `pdwAttributes`  
 接受 DWORD 指標`CSid`物件的屬性。 如果省略則為 NULL，將不會擷取屬性。  
  
### <a name="return-value"></a>傳回值  
 傳回 true 如果`CSid`找到，false 否則。  
  
### <a name="remarks"></a>備註  
 設定`pdwAttributes`到 NULL 提供一種確認是否存在`CSid`而不需存取屬性。 請注意，這個方法不應該用來檢查存取權限，因為不正確的結果可能會發生在 Windows 2000。 應用程式應該改用[CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership)方法。  
  
##  <a name="operator_eq"></a>CTokenGroups::operator =  
 指派運算子。  
  
```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```  
  
### <a name="parameters"></a>參數  
 `rhs`  
 `CTokenGroups`物件或[TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)結構以指派給`CTokenGroups`物件。  
  
### <a name="return-value"></a>傳回值  
 傳回更新`CTokenGroups`物件。  
  
##  <a name="operator_const_token_groups__star"></a>CTokenGroups::operator const TOKEN_GROUPS *  
 將指標值轉換**TOKEN_GROUPS**結構。  
  
```  
operator const TOKEN_GROUPS *() const throw(...);
```  
  
### <a name="remarks"></a>備註  
 將指標值轉換[TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624)結構。  
  
## <a name="see-also"></a>另請參閱  
 [安全性範例](../../visual-cpp-samples.md)   
 [CSid 類別](../../atl/reference/csid-class.md)   
 [類別概觀](../../atl/atl-class-overview.md)   
 [安全性的全域函式](../../atl/reference/security-global-functions.md)
