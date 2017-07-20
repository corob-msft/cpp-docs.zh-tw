---
title: "CRecordView 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecordView
- AFXDB/CRecordView
- AFXDB/CRecordView::CRecordView
- AFXDB/CRecordView::IsOnFirstRecord
- AFXDB/CRecordView::IsOnLastRecord
- AFXDB/CRecordView::OnGetRecordset
- AFXDB/CRecordView::OnMove
- AFXDB/CRecordView::OnMove
dev_langs:
- C++
helpviewer_keywords:
- CRecordView class
- ODBC recordsets, viewing records
- records, viewing ODBC
- views, ODBC
ms.assetid: 9b4b0897-bd50-4d48-a0b4-f3323f5ccc55
caps.latest.revision: 25
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
ms.openlocfilehash: 04ff47900037dcbaa12e2cba2c9a3e84caf54a69
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="crecordview-class"></a>CRecordView 類別
在控制項中顯示資料庫記錄的檢視。  
  
## <a name="syntax"></a>語法  
  
```  
class AFX_NOVTABLE CRecordView : public CFormView  
```  
  
## <a name="members"></a>Members  
  
### <a name="protected-constructors"></a>受保護的建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[CRecordView::CRecordView](#crecordview)|建構 `CRecordView` 物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[CRecordView::IsOnFirstRecord](#isonfirstrecord)|傳回非零，如果目前的記錄中相關聯的資料錄集的第一個記錄。|  
|[CRecordView::IsOnLastRecord](#isonlastrecord)|傳回非零，如果目前的記錄中相關聯的資料錄集的最後一個記錄。|  
|[CRecordView::OnGetRecordset](#ongetrecordset)|傳回從衍生的類別物件的指標`CRecordset`。 ClassWizard 您的覆寫這個函式，並在必要時建立資料錄集。|  
|[CRecordView::OnMove](#onmove)||  
  
### <a name="protected-methods"></a>保護方法  
  
|名稱|說明|  
|----------|-----------------|  
|[CRecordView::OnMove](#onmove)|如果目前資料錄已變更，更新資料來源上，則會移至指定的記錄 （下一個、 上一筆，第一個或最後一個）。|  
  
## <a name="remarks"></a>備註  
 檢視是表單檢視，直接連線到`CRecordset`物件。 檢視從對話方塊樣板資源建立，並顯示欄位的`CRecordset`對話方塊範本的控制項中的物件。 `CRecordView`物件用來自動化的表單上的控制項之間的資料錄集欄位的資料移動的對話方塊資料交換 (DDX) 和資料錄欄位交換 (RFX)。 `CRecordView`也提供的預設實作移動第一筆、 下一個、 上一個或最後一筆和更新記錄目前在檢視上的介面。  
  
> [!NOTE]
>  如果您正在使用的資料存取物件 (DAO) 類別，而不是開放式資料庫連接 (ODBC) 類別，使用類別[CDaoRecordView](../../mfc/reference/cdaorecordview-class.md)改。 如需詳細資訊，請參閱文章[概觀︰ 資料庫程式設計](../../data/data-access-programming-mfc-atl.md)。  
  
 若要建立資料錄檢視的最常見方式是使用應用程式精靈。 Tge 應用程式精靈建立資料錄檢視類別和其相關聯的資料錄集類別，做為入門的基本架構應用程式的一部分。 如果您不要使用應用程式精靈建立資料錄檢視類別，您稍後可以建立其與類別。 如果您只需要在單一表單時，應用程式精靈 的方法很容易的。 類別可讓您決定稍後在開發程序中使用資料錄檢視。 使用 ClassWizard 分別建立資料錄檢視和資料錄集，然後再將它們連線是最具彈性的方式，因為它讓您更能控制在資料錄集類別命名並將其。H /。CPP 檔案。 這個方法也可讓您有多個資料錄檢視上相同的資料錄集類別。  
  
 為了方便使用者在記錄間移動資料錄檢視中，應用程式精靈建立功能表 （或工具列） 移動的資源第一筆、 下一個、 上一個或最後一筆記錄。 如果您建立資料錄檢視類別與類別精靈，您需要這些資源自行建立具有功能表和點陣圖編輯器。  
  
 移動記錄記錄的預設實作的相關資訊，請參閱`IsOnFirstRecord`和`IsOnLastRecord`與發行項[使用資料錄檢視](../../data/using-a-record-view-mfc-data-access.md)。  
  
 `CRecordView`資料錄檢視才能更新使用者介面，則會追蹤的資料錄集的使用者的位置。 當使用者移至任一端的資料錄集時，資料錄檢視停用使用者介面物件，例如功能表項目或工具列按鈕 — 移動中相同的方向。  
  
 多個宣告和使用您的資料錄檢視和資料錄集類別的詳細資訊，請參閱 < 設計和建立資料錄檢視 >，文件中[資料錄檢視](../../data/record-views-mfc-data-access.md)。 如需如何記錄檢視的工作，以及如何使用它們的詳細資訊，請參閱文章[使用資料錄檢視](../../data/using-a-record-view-mfc-data-access.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 [CFormView](../../mfc/reference/cformview-class.md)  
  
 `CRecordView`  
  
## <a name="requirements"></a>需求  
 **標頭︰** afxdb.h  
  
##  <a name="crecordview"></a>CRecordView::CRecordView  
 當您建立的物件型別衍生自`CRecordView`，呼叫任一種形式的建構函式來初始化檢視的物件，並識別檢視所根據的對話方塊資源。  
  
```  
explicit CRecordView(LPCTSTR lpszTemplateName);  
explicit CRecordView(UINT nIDTemplate);
```  
  
### <a name="parameters"></a>參數  
 `lpszTemplateName`  
 包含的對話方塊範本資源名稱的 null 終止字串。  
  
 `nIDTemplate`  
 包含的對話方塊範本資源的 ID 編號。  
  
### <a name="remarks"></a>備註  
 依名稱 (pass 字串做為引數的建構函式) 或其 ID （不帶正負號的整數做為引數傳遞），您可能可以識別的資源。 資源識別碼被建議使用。  
  
> [!NOTE]
>  您的衍生的類別*必須*提供它自己的建構函式。 在衍生類別的建構函式，呼叫建構函式`CRecordView::CRecordView`資源名稱或識別碼做為引數，如下列範例所示。  
  
 **CRecordView::OnInitialUpdate**呼叫`UpdateData`，而它會呼叫`DoDataExchange`。 這個初始呼叫`DoDataExchange`連接`CRecordView`（間接） 可控制`CRecordset`欄位類別精靈所建立的資料成員。 在呼叫基底類別後，這些資料成員無法之前使用**CFormView::OnInitialUpdate**成員函式。  
  
> [!NOTE]
>  如果您使用類別精靈，精靈定義`enum`值`CRecordView::IDD`、 指定在類別宣告中，並用它在成員初始化清單中的建構函式。  
  
### <a name="example"></a>範例  
 [!code-cpp[NVC_MFCDatabase #&32;](../../mfc/codesnippet/cpp/crecordview-class_1.cpp)]  
  
##  <a name="isonfirstrecord"></a>CRecordView::IsOnFirstRecord  
 呼叫此成員函式，以判斷目前的記錄是第一筆記錄，此資料錄檢視相關聯的資料錄集物件中。  
  
```  
BOOL IsOnFirstRecord();
```  
  
### <a name="return-value"></a>傳回值  
 如果目前的記錄資料錄集; 第一筆記錄為非零否則為 0。  
  
### <a name="remarks"></a>備註  
 此函式可用來撰寫您自己的預設實作類別精靈所撰寫的命令更新處理常式。  
  
 如果使用者移到第一筆記錄，架構會停用您移至第一個或上一筆記錄有任何使用者介面物件。  
  
##  <a name="isonlastrecord"></a>CRecordView::IsOnLastRecord  
 呼叫此成員函式，以判斷目前的記錄是最後一筆記錄，此資料錄檢視相關聯的資料錄集物件中。  
  
```  
BOOL IsOnLastRecord();
```  
  
### <a name="return-value"></a>傳回值  
 如果目前的記錄資料錄集; 最後一筆記錄為非零否則為 0。  
  
### <a name="remarks"></a>備註  
 此函式可用來撰寫您自己的預設實作 ClassWizard 寫入支援移動記錄從使用者介面的命令更新處理常式。  
  
> [!CAUTION]
>  此函式的結果是可靠的不同之處在於檢視無法偵測到資料錄集的結尾，直到使用者已移動過。 資料錄檢視可以告訴它必須停用任何使用者介面物件移動到下一個或最後一筆記錄之前，使用者必須超越最後一筆記錄。 如果使用者移過去的最後一筆記錄，然後將傳回的最後一個記錄 （或之前），資料錄檢視可以追蹤使用者的資料錄集中的位置，並正確地停用使用者介面物件。 `IsOnLastRecord`實作函式的呼叫之後也不可靠**OnRecordLast**，處理`ID_RECORD_LAST`命令，或`CRecordset::MoveLast`。  
  
##  <a name="ongetrecordset"></a>CRecordView::OnGetRecordset  
 傳回的指標`CRecordset`-衍生的資料錄檢視相關聯的物件。  
  
```  
virtual CRecordset* OnGetRecordset() = 0;  
```  
  
### <a name="return-value"></a>傳回值  
 指標`CRecordset`-衍生物件，如果物件已成功建立，否則**NULL**指標。  
  
### <a name="remarks"></a>備註  
 您必須覆寫此成員函式建構或取得資料錄集物件並傳回的指標。 如果您宣告您的資料錄檢視類別與類別精靈，精靈會為您撰寫的預設值覆寫。 類別精靈的預設實作會傳回資料錄集的指標儲存在資料錄檢視中，如果有的話。 如果沒有，它會建構類型的資料錄集物件指定使用 ClassWizard 和呼叫其**開啟**成員函式以開啟資料表，或執行查詢，並再傳回物件的指標。  
  
 如需詳細資訊和範例，請參閱文章[資料錄檢視︰ 使用資料錄檢視](../../data/using-a-record-view-mfc-data-access.md)。  
  
##  <a name="onmove"></a>CRecordView::OnMove  
 呼叫此成員函式，將移至不同的資料錄集，資料錄檢視控制項中顯示其欄位。  
  
```  
virtual BOOL OnMove(UINT nIDMoveCommand);
```  
  
### <a name="parameters"></a>參數  
 `nIDMoveCommand`  
 它有下列標準命令 ID 值︰  
  
- `ID_RECORD_FIRST`移至資料錄集的第一個記錄。  
  
- `ID_RECORD_LAST`資料錄集中移動至最後一筆記錄。  
  
- `ID_RECORD_NEXT`移至資料錄集的下一個記錄。  
  
- `ID_RECORD_PREV`移至資料錄集的上一個記錄。  
  
### <a name="return-value"></a>傳回值  
 非零，如果移動成功。否則為 0，表示移動要求遭到拒絕。  
  
### <a name="remarks"></a>備註  
 預設實作會呼叫適當**移動**成員函式`CRecordset`資料錄檢視相關聯的物件。  
  
 根據預設，`OnMove`更新目前的記錄資料來源上，如果使用者資料錄檢視中已變更。  
  
 應用程式精靈建立功能表資源與第一筆、 最後一筆記錄、 下一筆記錄和上一筆記錄的功能表項目。 如果您選取可停駐工具列選項時，應用程式精靈會建立工具列按鈕對應至這些命令。  
  
 如果您跳過資料錄集中的最後一筆記錄時，資料錄檢視會繼續顯示最後一筆記錄。 如果您向後跳過第一筆記錄，資料錄檢視會繼續顯示第一筆記錄。  
  
> [!CAUTION]
>  呼叫`OnMove`擲回例外狀況，如果資料錄集沒有任何記錄。 呼叫適當的使用者介面更新處理常式函式 — **OnUpdateRecordFirst**， **OnUpdateRecordLast**， **OnUpdateRecordNext**，或**OnUpdateRecordPrev** — 在對應的移動作業，以判斷資料錄集是否有任何記錄。  
  
## <a name="see-also"></a>另請參閱  
 [CFormView 類別](../../mfc/reference/cformview-class.md)   
 [階層架構圖表](../../mfc/hierarchy-chart.md)   
 [CRecordset 類別](../../mfc/reference/crecordset-class.md)   
 [CFormView 類別](../../mfc/reference/cformview-class.md)
