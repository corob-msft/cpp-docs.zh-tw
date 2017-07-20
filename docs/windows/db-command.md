---
title: "db_command | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.db_command"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "db_command 屬性"
ms.assetid: 714c3e15-85d7-408b-9a7c-88505c3e5d24
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# db_command
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

建立 OLE DB 命令。  
  
## 語法  
  
```  
  
[ db_command(   
command  
,   
   name  
,   
   source_name  
,   
   hresult  
,   
   bindings  
,   
   bulk_fetch  
)  
]  
  
```  
  
#### 參數  
 `command`  
 包含 OLE DB 命令文字的命令字串。 簡單範例如下︰  
  
```  
[ db_command ( command = "Select * from Products" ) ]  
```  
  
 *command* 語法如下：  
  
```  
binding parameter block 1  
   OLE DB command  
binding parameter block 2  
   continuation of OLE DB command  
binding parameter block 3  
...  
```  
  
 *「繫結參數區塊」*\(binding parameter block\) 定義如下︰  
  
 **\(\[** `bindtype` **\]** *szVar1* \[*, szVar2* \[, *nVar3* \[, ...\]\]\] **\)**  
  
 其中：  
  
 **\(** 標示資料繫結區塊的開始。  
  
 **\[** `bindtype` **\]** 是下列其中一個不區分大小寫的字串：  
  
-   **\[db\_column\]** 會將每個成員變數繫結至資料列集中的資料行。  
  
-   **\[bindto\]** \(與 **\[db\_column\]** 相同\)。  
  
-   **\[in\]** 會將成員變數繫結為輸入參數。  
  
-   **\[out\]** 會將成員變數繫結為輸出參數。  
  
-   **\[in,out\]** 會將成員變數繫結為輸入\/輸出參數。  
  
 *SzVarX* 會解析為目前範圍內的成員變數。  
  
 **\)** 標示資料繫結區塊的結束。  
  
 如果命令字串包含一或多個規範 \(如 \[in\]、\[out\] 或 \[in\/out\]\)，則 **db\_command** 會建置參數對應。  
  
 如果命令字串包含一或多個參數 \(如 \[db\_column\] 或 \[bindto\]\)，則 **db\_command** 會產生一個資料列集和一個存取子對應來服務這些繫結的變數。 如需詳細資訊，請參閱 [db\_accessor](../windows/db-accessor.md)。  
  
> [!NOTE]
>  在類別層級使用 **db\_command** 時，\[`bindtype`\] 語法和 `bindings` 參數無效。  
  
 以下是繫結參數區塊的一些範例。 下列範例會將 `m_au_fname` 和 `m_au_lname` 資料成員分別繫結至 pubs 資料庫中 authors 資料表的 `au_fname` 和 `au_lname` 資料行：  
  
```  
TCHAR m_au_fname[21];  
TCHAR m_au_lname[41];  
TCHAR m_state[3] = 'CA';  
  
[db_command (  
   command = "SELECT au_fname([bindto]m_au_fname), au_lname([bindto]m_au_lname) " \  
   "FROM dbo.authors " \  
   "WHERE state = ?([in]m_state)")  
```  
  
 \]  
  
 *name* \(選擇性\)  
 您用來處理資料列集之控制代碼的名稱。 如果您指定 *name*，則 **db\_command** 會產生具有所指定 *name* 的類別，以用來周遊資料列集或執行多個動作查詢。 如果您未指定 *name*，則不可能會將多個資料列的結果傳回給使用者。  
  
 *source\_name* \(選擇性\)  
 命令所執行的 `CSession` 變數或已套用 `db_source` 屬性的類別執行個體。 請參閱 [db\_source](../windows/db-source.md)。  
  
 **db\_command** 會確認用於 *source\_name* 的變數有效，因此指定的變數應該在函式或全域範圍中。  
  
 `hresult` \(選擇性\)  
 識別將接收此資料庫命令之 `HRESULT` 的變數。 如果變數不存在，則屬性會自動予以插入。  
  
 *bindings* \(選擇性\)  
 可讓您區隔繫結參數與 OLE DB 命令。  
  
 如果您指定 `bindings` 的值，則 **db\_command** 會剖析相關聯的值，而不會剖析 \[`bindtype`\] 參數。 這種用法可讓您使用 OLE DB 提供者語法。 若要停用剖析，而不使用繫結參數，請指定 **Bindings\=""**。  
  
 如果您未指定 `bindings` 的值，則 **db\_command** 會剖析繫結參數區塊，並尋找 '**\(**'，後面依序接著以括弧括住的 **\[**`bindtype`**\]**、一或多個先前宣告的 C\+\+ 成員變數，以及 '**\)**'。 產生的命令中會移除括弧之間的所有文字，並且會使用這些參數來建構此命令的資料行和參數繫結。  
  
 *bulk\_fetch* \(選擇性\)  
 指定要提取之資料列數目的整數值。  
  
 預設值為 1，指定單一資料列擷取 \(資料列集的類型會是 [CRowset](../data/oledb/crowset-class.md)\)。  
  
 大於 1 的值指定大量資料列擷取。 大量資料列擷取指的是大量資料列集可以擷取多個資料列處理代碼 \(資料列集的類型會是 [CBulkRowset](../data/oledb/cbulkrowset-class.md)，並且呼叫具有所指定數目的資料列的 `SetRows`\)。  
  
 如果 *bulk\_fetch* 小於 1，則 `SetRows` 會傳回零。  
  
## 備註  
 **db\_command** 會建立 OLE DB 消費者用來執行命令的 [CCommand](../data/oledb/ccommand-class.md) 物件。  
  
 您可以搭配使用 **db\_command** 與類別或函式範圍；主要差異在於 `CCommand` 物件的範圍。 使用函式範圍時，繫結這類資料會終止於函式結尾。 類別和函式範圍用法都包含 OLE DB 消費者範本類別 **CCommand\<\>**，但函式和類別案例的範本引數不同。 在函式案例中，將會繫結至包含區域變數的 **Accessor**，類別用法則會將 `CAccessor` 衍生類別推斷為引數。 當成類別屬性使用時，**db\_command** 是與 **db\_column** 搭配運作。  
  
 **db\_command** 可以用來執行不傳回結果集的命令。  
  
 消費者屬性提供者將此屬性套用至類別時，編譯器會將類別重新命名為 \_*YourClassName*Accessor \(其中 *YourClassName* 是您提供的類別名稱\)，而且編譯器也會建立稱為 *YourClassName* 的類別，其衍生自 \_*YourClassName*Accessor。  在 \[類別\] 檢視中，您會看到這兩個類別。  
  
## 範例  
 此範例所定義的命令會從狀態資料行符合 'CA' 的表格中選取第一個和最後一個名稱。**db\_command** 會建立和讀取可呼叫精靈所產生的函式 \(例如 [OpenAll and CloseAll](../data/oledb/consumer-wizard-generated-methods.md)\) 以及 `CRowset` 成員函式 \(例如 [MoveNext](../data/oledb/crowset-movenext.md)\) 的資料列集。  
  
 請注意，此程式碼需要您提供連接至 pubs 資料庫的連接字串。 如需如何在開發環境中執行這項作業的資訊，請參閱 [How to: Connect to a Database from Server Explorer](http://msdn.microsoft.com/zh-tw/7c1c3067-0d77-471b-872b-639f9f50db74) 和 [How to: Add New Data Connections in Server Explorer\/Database Explorer](http://msdn.microsoft.com/zh-tw/fb2f513b-ddad-4142-911e-856bba0054c8)。  
  
```  
// db_command.h  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
  
#pragma once  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
  
struct CAuthors {  
   // In order to fix several issues with some providers, the code below may bind  
   // columns in a different order than reported by the provider  
  
   DBSTATUS m_dwau_lnameStatus;  
   DBSTATUS m_dwau_fnameStatus;  
   DBLENGTH m_dwau_lnameLength;  
   DBLENGTH m_dwau_fnameLength;  
  
   [ db_column("au_lname", status="m_dwau_lnameStatus", length="m_dwau_lnameLength") ] TCHAR m_au_lname[41];  
   [ db_column("au_fname", status="m_dwau_fnameStatus", length="m_dwau_fnameLength") ] TCHAR m_au_fname[21];  
  
   [ db_param("7", paramtype="DBPARAMIO_INPUT") ] TCHAR m_state[3];  
  
   void GetRowsetProperties(CDBPropSet* pPropSet) {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   }  
};  
```  
  
## 範例  
  
```  
// db_command.cpp  
// compile with: /c  
#include "db_command.h"  
  
int main(int argc, _TCHAR* argv[]) {  
   HRESULT hr = CoInitialize(NULL);  
  
   // Instantiate rowset  
   CAuthors rs;  
  
   // Open rowset and move to first row  
   strcpy_s(rs.m_state, sizeof(rs.m_state), _T("CA"));  
   hr = rs.OpenAll();  
   hr = rs.MoveFirst();  
  
   // Iterate through the rowset  
   while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET ) {  
      // Print out the column information for each row  
      printf("First Name: %s, Last Name: %s\n", rs.m_au_fname, rs.m_au_lname);  
      hr = rs.MoveNext();  
   }  
  
   rs.CloseAll();  
   CoUninitialize();  
}  
```  
  
## 範例  
 此範例會在資料來源類別 `CMySource` 上使用 `db_source`，並在命令類別 `CCommand1` 和 `CCommand2` 上使用 `db_command`。  
  
```  
// db_command_2.cpp  
// compile with: /c  
#include <atlbase.h>  
#include <atlplus.h>  
#include <atldbcli.h>  
// class usage for both db_source and db_command  
  
[  db_source(L"your connection string"),  
   db_command(L" \  
      SELECT au_lname, au_fname \  
      FROM dbo.authors \  
      WHERE state = 'CA'")  ]  
struct CMySource {  
   HRESULT OpenDataSource() {  
      return S_OK;  
   }  
};  
  
[db_command(command = "SELECT * FROM Products")]  
class CCommand1 {};  
  
[db_command(command = "SELECT FNAME, LNAME FROM Customers")]  
class CCommand2 {};  
  
int main() {  
   CMySource s;  
   HRESULT hr = s.OpenDataSource();  
   if (SUCCEEDED(hr)) {  
      CCommand1 c1;  
      hr = c1.Open(s);  
  
      CCommand2 c2;  
      hr = c2.Open(s);  
   }  
  
   s.CloseDataSource();  
}  
```  
  
## 需求  
  
### 屬性內容  
  
|||  
|-|-|  
|**適用於**|**class**、`struct`、member、method、local|  
|**可重複**|否|  
|**必要屬性**|無|  
|**無效屬性**|無|  
  
 如需有關屬性內容的詳細資訊，請參閱[屬性內容](../windows/attribute-contexts.md)。  
  
## 請參閱  
 [OLE DB Consumer Attributes](../windows/ole-db-consumer-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](http://msdn.microsoft.com/zh-tw/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)