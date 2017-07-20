---
title: "消費者精靈產生的類別 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "插入屬性的類別和方法"
  - "精靈產生的類別和方法"
  - "OLE DB 消費者, 精靈產生的類別和方法"
  - "OLE DB 消費者中的命令類別"
  - "類別 [C++], OLE DB 消費者精靈產生的"
  - "消費者精靈產生的類別和方法"
  - "OLE DB 消費者中的使用者資料錄類別"
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 消費者精靈產生的類別
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

當您使用 \[ATL OLE DB 消費者精靈\] 產生消費者時，您可以選擇使用 OLE DB 樣板或 OLE DB 屬性。 在這兩種情況下，精靈都會產生一個命令類別和一個使用者記錄類別。 命令類別包含程式碼，可以開啟資料來源和您在精靈中指定的資料列集。 使用者記錄類別包含您所選取之資料庫資料表的資料行對應。 不過，所產生的程式碼在每個案例中會有所不同：  
  
-   如果您選取樣板化消費者，精靈會產生一個命令類別和一個使用者記錄類別。 命令類別會具有您在精靈的 \[類別\] 方塊中輸入的名稱 \(例如 `CProducts`\)，而使用者記錄類別的名稱則以 "*ClassName*Accessor" 格式表示 \(例如 `CProductsAccessor`\)。 這兩個類別都會放在消費者的標頭檔。  
  
-   如果您選取屬性化消費者，使用者記錄類別的名稱將以 "\_*ClassName*Accessor" 格式表示，且將會插入。 也就是說，您將只能在文字編輯器中檢視命令類別。您只能以插入程式碼的方式檢視使用者記錄類別。 如需檢視插入程式碼的相關資訊，請參閱[插入程式碼偵錯](../Topic/How%20to:%20Debug%20Injected%20Code.md)。  
  
 下列範例使用在 Northwind 資料庫的 Products 資料表建立的命令類別，來示範命令類別和使用者記錄類別的精靈產生的消費者程式碼。  
  
## 樣板化的使用者記錄類別  
 如果您使用 OLE DB 樣板 \(而不是 OLE DB 屬性\) 來建立 OLE DB 消費者，精靈會如本節所述產生程式碼。  
  
### 資料行的資料成員  
 使用者記錄類別的第一個部分，包含資料成員宣告與每個資料繫結資料行的狀態和長度資料成員。 如需這些資料成員的相關資訊，請參閱[精靈產生的存取子中的欄位狀態資料成員](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)。  
  
> [!NOTE]
>  如果您修改使用者記錄類別或撰寫自己的消費者，資料變數必須出現在狀態和長度變數之前。  
  
> [!NOTE]
>  \[ATL OLE DB 消費者精靈\] 使用 **DB\_NUMERIC** 類型來繫結數值資料類型。 它先前使用 **DBTYPE\_VARNUMERIC** \(**DB\_VARNUMERIC** 類型所述的格式；請參閱 Oledb.h\)。 如果您不使用精靈來建立消費者，建議您使用 **DB\_NUMERIC**。  
  
```  
// Products.H : Declaration of the CProducts class class CProductsAccessor { public: // Column data members: LONG m_ProductID; TCHAR m_ProductName[41]; LONG m_SupplierID; LONG m_CategoryID; TCHAR m_QuantityPerUnit[21]; CURRENCY m_UnitPrice; SHORT m_UnitsInStock; SHORT m_UnitsOnOrder; SHORT m_ReorderLevel; VARIANT_BOOL m_Discontinued; // Column status data members: DBSTATUS m_dwProductIDStatus; DBSTATUS m_dwProductNameStatus; DBSTATUS m_dwSupplierIDStatus; DBSTATUS m_dwCategoryIDStatus; DBSTATUS m_dwQuantityPerUnitStatus; DBSTATUS m_dwUnitPriceStatus; DBSTATUS m_dwUnitsInStockStatus; DBSTATUS m_dwUnitsOnOrderStatus; DBSTATUS m_dwReorderLevelStatus; DBSTATUS m_dwDiscontinuedStatus; // Column length data members: DBLENGTH m_dwProductIDLength; DBLENGTH m_dwProductNameLength; DBLENGTH m_dwSupplierIDLength; DBLENGTH m_dwCategoryIDLength; DBLENGTH m_dwQuantityPerUnitLength; DBLENGTH m_dwUnitPriceLength; DBLENGTH m_dwUnitsInStockLength; DBLENGTH m_dwUnitsOnOrderLength; DBLENGTH m_dwReorderLevelLength; DBLENGTH m_dwDiscontinuedLength;  
```  
  
### 資料列集屬性  
 接下來，精靈會設定資料列集屬性。 如果您在 \[ATL OLE DB 消費者精靈\] 中選取了 \[變更\]、\[插入\] 或 \[刪除\]，在這裡會設定適當的屬性 \(一律會設定 DBPROP\_IRowsetChange，然後分別為 DBPROPVAL\_UP\_CHANGE、DBPROPVAL\_UP\_INSERT 和\/或 DBPROPVAL\_UP\_DELETE 的其中一或多個\)。  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet) { pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL); pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE); }  
```  
  
### 命令或資料表類別  
 如果您指定命令類別，精靈會宣告命令類別。對於樣板化程式碼，命令看起來如下：  
  
```  
DEFINE_COMMAND_EX(CProductsAccessor, L" \ SELECT \ ProductID, \ ProductName, \ SupplierID, \ CategoryID, \ QuantityPerUnit, \ UnitPrice, \ UnitsInStock, \ UnitsOnOrder, \ ReorderLevel, \ Discontinued \ FROM dbo.Products")  
```  
  
### 資料行對應  
 接著精靈將產生資料行繫結或資料行對應。 為了修正某些提供者的幾個問題，下列程式碼可能會以和提供者所報告的不同順序來繫結資料行。  
  
```  
BEGIN_COLUMN_MAP(CProductsAccessor) COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus) COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus) COLUMN_ENTRY_LENGTH_STATUS(3, m_SupplierID, m_dwSupplierIDLength, m_dwSupplierIDStatus) COLUMN_ENTRY_LENGTH_STATUS(4, m_CategoryID, m_dwCategoryIDLength, m_dwCategoryIDStatus) COLUMN_ENTRY_LENGTH_STATUS(5, m_QuantityPerUnit, m_dwQuantityPerUnitLength, m_dwQuantityPerUnitStatus) _COLUMN_ENTRY_CODE(6, DBTYPE_CY, _SIZE_TYPE(m_UnitPrice), 0, 0, offsetbuf(m_UnitPrice), offsetbuf(m_dwUnitPriceLength), offsetbuf(m_dwUnitPriceStatus)) COLUMN_ENTRY_LENGTH_STATUS(7, m_UnitsInStock, m_dwUnitsInStockLength, m_dwUnitsInStockStatus) COLUMN_ENTRY_LENGTH_STATUS(8, m_UnitsOnOrder, m_dwUnitsOnOrderLength, m_dwUnitsOnOrderStatus) COLUMN_ENTRY_LENGTH_STATUS(9, m_ReorderLevel, m_dwReorderLevelLength, m_dwReorderLevelStatus) _COLUMN_ENTRY_CODE(10, DBTYPE_BOOL, _SIZE_TYPE(m_Discontinued), 0, 0, offsetbuf(m_Discontinued), offsetbuf(m_dwDiscontinuedLength), offsetbuf(m_dwDiscontinuedStatus)) END_COLUMN_MAP() };  
```  
  
### 類別宣告  
 最後，精靈會產生命令類別宣告，如下所示：  
  
```  
class CProducts : public CCommand<CAccessor<CProductsAccessor> >  
```  
  
## 插入屬性的使用者記錄類別  
 如果您使用資料庫屬性 \([db\_command](../../windows/db-command.md) 或 [db\_table](../../windows/db-table.md)\) 來建立 OLE DB 消費者，屬性會插入使用者記錄類別，且其名稱將為 "\_*ClassName*Accessor" 的形式。 例如，如果您將命令類別命名為 `COrders`，則使用者記錄類別將為 `_COrdersAccessor`。 雖然使用者記錄類別會出現在類別檢視中，但按兩下它即可巡覽至標頭檔中的命令或資料表類別。 在這些情況下，您只能藉由檢視插入屬性的程式碼，來檢視使用者記錄類別的實際宣告。  
  
 如果您加入或覆寫屬性化消費者的方法，可能會有潛在的錯亂。 例如，您可以將 `_COrdersAccessor` 建構函式加入 `COrders` 宣告，但請注意，事實上這會將建構函式加入插入的 `COrdersAccessor` 類別。 這類建構函式可以初始化資料行\/參數，但您無法這樣建立複製建構函式，因為它無法直接具現化 `COrdersAccessor` 物件。 如果您需要直接在 `COrders` 類別上的建構函式 \(或其他方法\)，建議您定義衍生自 `COrders` 的新類別，並在那裡加入必要的方法。  
  
 在下列範例中，精靈會產生類別 `COrders` 的宣告，但因為屬性將其插入，所以不會出現使用者記錄類別 `COrdersAccessor`。  
  
```  
#define _ATL_ATTRIBUTES #include <atlbase.h> #include <atldbcli.h> [ db_source(L"your connection string"), db_command(L"Select ShipName from Orders;") ] class COrders { public: // COrders()            // incorrect constructor name _COrdersAccessor()      // correct constructor name { } [db_column(1) ] TCHAR m_ShipName[41]; };  
```  
  
 插入的命令類別宣告看起來如下：  
  
```  
class CProducts : public CCommand<CAccessor<_CProductsAccessor> >  
```  
  
 大部分的插入程式碼與樣板化版本相同或類似。 主要的差別在於插入的方法，如[消費者精靈產生的方法](../../data/oledb/consumer-wizard-generated-methods.md)中所述。  
  
 如需檢視插入程式碼的相關資訊，請參閱[插入程式碼偵錯](../Topic/How%20to:%20Debug%20Injected%20Code.md)。  
  
## 請參閱  
 [使用精靈建立 OLE DB 消費者](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)