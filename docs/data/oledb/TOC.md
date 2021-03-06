# [OLE DB 程式設計](ole-db-programming.md)
## [OLE DB 程式設計概觀](ole-db-programming-overview.md)
### [OLE DB 消費者和提供者](ole-db-consumers-and-providers.md)
### [OLE DB 物件模型](ole-db-object-model.md)
### [OLE DB 範本、屬性和其他實作](ole-db-templates-attributes-and-other-implementations.md)
### [OLE DB 架構設計問題](ole-db-architectural-design-issues.md)
## [OLE DB 消費者範本 (C++)](ole-db-consumer-templates-cpp.md)
### [資料來源和工作階段](data-sources-and-sessions.md)
### [存取子和資料列集](accessors-and-rowsets.md)
### [命令和資料表](commands-and-tables.md)
### [使用者資料錄](user-records.md)
### [結構描述資料列集](schema-rowsets.md)
### [建立 OLE DB 消費者](creating-an-ole-db-consumer.md)
#### [使用精靈建立 OLE DB 消費者](creating-an-ole-db-consumer-using-a-wizard.md)
##### [建立簡單消費者](creating-a-simple-consumer.md)
##### [實作簡單消費者](implementing-a-simple-consumer.md)
##### [消費者精靈產生的類別](consumer-wizard-generated-classes.md)
##### [消費者精靈產生的方法](consumer-wizard-generated-methods.md)
#### [未使用精靈建立消費者](creating-a-consumer-without-using-a-wizard.md)
### [使用 OLE DB 消費者範本](working-with-ole-db-consumer-templates.md)
#### [以資料庫屬性簡化資料存取](simplifying-data-access-with-database-attributes.md)
#### [在精靈產生的存取子中的欄位狀態資料成員](field-status-data-members-in-wizard-generated-accessors.md)
#### [往返簡單資料列集](traversing-a-simple-rowset.md)
#### [發出參數型查詢](issuing-a-parameterized-query.md)
#### [擷取資料](fetching-data.md)
#### [更新資料列集](updating-rowsets.md)
#### [使用預存程序](using-stored-procedures.md)
##### [定義預存程序](defining-stored-procedures.md)
##### [輸出參數](output-parameters.md)
##### [從預存程序使用多重結果集](using-multiple-result-sets-from-one-stored-procedure.md)
#### [使用存取子](using-accessors.md)
##### [決定使用哪一種存取子](determining-which-type-of-accessor-to-use.md)
##### [在資料列集上使用多重存取子](using-multiple-accessors-on-a-rowset.md)
##### [使用動態存取子](using-dynamic-accessors.md)
##### [覆寫動態存取子](overriding-a-dynamic-accessor.md)
##### [使用手動存取子](using-manual-accessors.md)
##### [存取 XML 資料](accessing-xml-data.md)
#### [使用結構描述資料列集取得中繼資料](obtaining-metadata-with-schema-rowsets.md)
#### [支援 OLE DB 中的異動](supporting-transactions-in-ole-db.md)
#### [使用 OLE DB 資料錄檢視](using-ole-db-record-views.md)
#### [使用現有的 ADO 資料錄集](using-an-existing-ado-recordset.md)
#### [在其他資料表包含資料列參考時更新資料行](updating-a-column-when-another-table-contains-a-reference-to-the-row.md)
#### [使用書籤](using-bookmarks.md)
#### [擷取 BLOB](retrieving-a-blob.md)
#### [接收通知](receiving-notifications.md)
## [OLE DB 提供者範本 (C++)](ole-db-provider-templates-cpp.md)
### [OLE DB 提供者範本架構](ole-db-provider-template-architecture.md)
#### [資料來源物件介面](data-source-object-interfaces.md)
#### [工作階段物件介面](session-object-interfaces.md)
#### [資料列集物件介面](rowset-object-interfaces.md)
#### [命令物件介面](command-object-interfaces.md)
#### [異動物件介面](transaction-object-interfaces.md)
#### [屬性對應](property-maps.md)
#### [使用者資料錄](user-record.md)
### [建立 OLE DB 提供者](creating-an-ole-db-provider.md)
#### [為提供者建立專案](creating-a-project-for-the-provider.md)
#### [建立提供者](creating-the-provider.md)
#### [提供者精靈產生的檔案](provider-wizard-generated-files.md)
##### [CCustomSource (CustomDS.H)](cmyprovidersource-myproviderds-h.md)
##### [CCustomSession (CustomSess.H)](cmyprovidersession-myprovidersess-h.md)
##### [CCustomCommand (CustomRS.H)](cmyprovidercommand-myproviderrs-h.md)
##### [CCustomRowset (CustomRS.H)](cmyproviderrowset-myproviderrs-h.md)
##### [CCustomWindowsFile](cmyproviderwindowsfile.md)
#### [建立簡單唯讀提供者](creating-a-simple-read-only-provider.md)
##### [實作簡單唯讀提供者](implementing-the-simple-read-only-provider.md)
###### [將字串儲存於 OLE DB 提供者內](storing-strings-in-the-ole-db-provider.md)
###### [將字串讀入 OLE DB 提供者內](reading-strings-into-the-ole-db-provider.md)
##### [增強簡單唯讀提供者](enhancing-the-simple-read-only-provider.md)
###### [修改 RCustomRowset 的繼承](modifying-the-inheritance-of-rmyproviderrowset.md)
###### [動態決定傳回給消費者的資料行](dynamically-determining-columns-returned-to-the-consumer.md)
##### [測試唯讀提供者](testing-the-read-only-provider.md)
#### [建立可更新的提供者](creating-an-updatable-provider.md)
### [使用 OLE DB 提供者範本](working-with-ole-db-provider-templates.md)
#### [將介面新增至提供者](adding-an-interface-to-your-provider.md)
#### [在提供者內參考屬性](referencing-a-property-in-your-provider.md)
#### [在提供者內設定屬性](setting-properties-in-your-provider.md)
#### [在提供者內動態繫結資料行](dynamically-binding-columns-in-your-provider.md)
#### [在提供者內支援無限制執行緒](supporting-free-threading-in-your-provider.md)
#### [測試提供者](testing-your-provider.md)
#### [偵錯提供者](debugging-your-provider.md)
#### [轉換提供者不支援的資料](converting-data-not-supported-by-the-provider.md)
### [進階的提供者技術](advanced-provider-techniques.md)
#### [支援通知](supporting-notifications.md)
#### [支援結構描述資料列集](supporting-schema-rowsets.md)
#### [提供者書籤支援](provider-support-for-bookmarks.md)
#### [通過 OLE DB 一致性測試](passing-ole-db-conformance-tests.md)
#### [OLE DB 資源共用和服務](ole-db-resource-pooling-and-services.md)
##### [OLE DB 應用程式的資源共用](resource-pooling-in-your-ole-db-application.md)
##### [啟用和停用 OLE DB 服務](enabling-and-disabling-ole-db-services.md)
###### [啟用和停用提供者的服務](enabling-and-disabling-services-for-a-provider.md)
###### [覆寫提供者服務預設值](overriding-provider-service-defaults.md)
# [OLE DB 範本](ole-db-templates.md)
## [OLE DB 消費者範本參考](ole-db-consumer-templates-reference.md)
### [CAccessor 類別](caccessor-class.md)
### [CAccessorBase 類別](caccessorbase-class.md)
### [CAccessorRowset 類別](caccessorrowset-class.md)
### [CArrayRowset 類別](carrayrowset-class.md)
### [CBookmark 類別](cbookmark-class.md)
### [CBulkRowset 類別](cbulkrowset-class.md)
### [CColumnAccessor 類別](ccolumnaccessor-class.md)
### [CCommand 類別](ccommand-class.md)
### [CDataConnection 類別](cdataconnection-class.md)
### [CDataSource 類別](cdatasource-class.md)
### [CDBErrorInfo 類別](cdberrorinfo-class.md)
### [CDBPropIDSet 類別](cdbpropidset-class.md)
### [CDBPropSet 類別](cdbpropset-class.md)
### [CDynamicAccessor 類別](cdynamicaccessor-class.md)
### [CDynamicParameterAccessor 類別](cdynamicparameteraccessor-class.md)
### [CDynamicStringAccessor 類別](cdynamicstringaccessor-class.md)
### [CDynamicStringAccessorA 類別](cdynamicstringaccessora-class.md)
### [CDynamicStringAccessorW 類別](cdynamicstringaccessorw-class.md)
### [CEnumerator 類別](cenumerator-class.md)
### [CEnumeratorAccessor 類別](cenumeratoraccessor-class.md)
### [CManualAccessor 類別](cmanualaccessor-class.md)
### [CMultipleResults 類別](cmultipleresults-class.md)
### [CNoAccessor 類別](cnoaccessor-class.md)
### [CNoMultipleResults 類別](cnomultipleresults-class.md)
### [CNoRowset 類別](cnorowset-class.md)
### [CRestrictions 類別](crestrictions-class.md)
### [CRowset 類別](crowset-class.md)
### [CSession 類別](csession-class.md)
### [CStreamRowset 類別](cstreamrowset-class.md)
### [CTable 類別](ctable-class.md)
### [CXMLAccessor 類別](cxmlaccessor-class.md)
### [IRowsetNotifyImpl 類別](irowsetnotifyimpl-class.md)
### [結構描述資料列集類別和 Typedef 類別](schema-rowset-classes-and-typedef-classes.md)
### [OLE DB 消費者範本的巨集和全域函式](macros-and-global-functions-for-ole-db-consumer-templates.md)
## [OLE DB 提供者範本參考](ole-db-provider-templates-reference.md)
### [CRowsetImpl 類別](crowsetimpl-class.md)
### [CSimpleRow 類別](csimplerow-class.md)
### [CUtlProps 類別](cutlprops-class.md)
### [IAccessorImpl 類別](iaccessorimpl-class.md)
### [IColumnsInfoImpl 類別](icolumnsinfoimpl-class.md)
### [ICommandImpl 類別](icommandimpl-class.md)
### [ICommandPropertiesImpl 類別](icommandpropertiesimpl-class.md)
### [ICommandTextImpl 類別](icommandtextimpl-class.md)
### [IConvertTypeImpl 類別](iconverttypeimpl-class.md)
### [IDBCreateCommandImpl 類別](idbcreatecommandimpl-class.md)
### [IDBCreateSessionImpl 類別](idbcreatesessionimpl-class.md)
### [IDBInitializeImpl 類別](idbinitializeimpl-class.md)
### [IDBPropertiesImpl 類別](idbpropertiesimpl-class.md)
### [IDBSchemaRowsetImpl 類別](idbschemarowsetimpl-class.md)
### [IErrorRecordsImpl 類別](ierrorrecordsimpl-class.md)
### [IGetDataSourceImpl 類別](igetdatasourceimpl-class.md)
### [IOpenRowsetImpl 類別](iopenrowsetimpl-class.md)
### [IRowsetChangeImpl 類別](irowsetchangeimpl-class.md)
### [IRowsetCreatorImpl 類別](irowsetcreatorimpl-class.md)
### [IRowsetIdentityImpl 類別](irowsetidentityimpl-class.md)
### [IRowsetImpl 類別](irowsetimpl-class.md)
### [IRowsetInfoImpl 類別](irowsetinfoimpl-class.md)
### [IRowsetLocateImpl 類別](irowsetlocateimpl-class.md)
### [IRowsetNotifyCP 類別](irowsetnotifycp-class.md)
### [IRowsetUpdateImpl 類別](irowsetupdateimpl-class.md)
### [ISessionPropertiesImpl 類別](isessionpropertiesimpl-class.md)
### [OLE DB 提供者範本的巨集](macros-for-ole-db-provider-templates.md)
