---
title: "加入方法精靈 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.method.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "加入方法精靈 [C++]"
  - "方法 [C++], 使用精靈加入"
ms.assetid: b9a71b0e-9ecf-40fa-9f86-4200cb23d671
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 加入方法精靈
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

使用這個精靈來將方法加入介面。  依據要加入方法的專案類型或介面型別，此精靈將顯示不同的選項。  
  
## 名稱  
 **傳回型別**  
 由該方法傳回的資料型別。  建議對所有介面型別使用 `HRESULT`，因為它提供了傳回錯誤的標準方法。  
  
|介面型別|描述|  
|----------|--------|  
|雙重介面|`HRESULT`.  無法變更。|  
|自訂介面|`HRESULT`.  無法變更。|  
|本機自訂介面|提供自訂的傳回型別，或從清單上選取。|  
|分配介面|提供自訂的傳回型別，或從清單上選取。|  
|MFC ActiveX 控制項分配介面|如果您實作一個內建方法，則傳回型別會設定成適當的值，且無法變更它。  如果您從 \[方法名稱\] 清單上選取一個方法，並且按一下 \[選擇方法型別\] 下的 \[自訂\]，則請從清單上選取一個傳回型別。|  
  
 **方法名稱**  
 設定此方法的名稱。  
  
|介面型別|描述|  
|----------|--------|  
|ATL 雙重介面、自訂介面和本機自訂介面|提供自訂的方法名稱。|  
|MFC 分配介面|提供自訂的方法名稱或從清單上選取建議的方法名稱。  如果您從清單上選取一個名稱，\[傳回型別\] 方塊內會出現適當的數值，並且無法變更它。|  
|MFC ActiveX 控制項分配介面|提供自訂的方法或選取 [DoClick](../Topic/COleControl::DoClick.md) 和 [Refresh](../Topic/COleControl::Refresh.md) 任一種內建方法。  如需詳細資訊，請參閱 [MFC ActiveX 控制項：加入內建方法](../mfc/mfc-activex-controls-adding-stock-methods.md)。|  
  
 **方法型別**  
 只有 MFC ActiveX 控制項可以使用。  如果您在 \[方法名稱\] 方塊中提供一個方法名稱，而非從清單上選取一個方法，則此方塊無法使用。  
  
 如果您在 \[方法名稱\] 清單上選取其中一個方法，請選取內建實作 \(Implementation\) 或自訂實作。  
  
|方法型別|描述|  
|----------|--------|  
|**內建**|預設值。  在 \[方法名稱\] 清單中插入您選取之方法的內建實作。  如果您選取 \[內建\]，則無法變更 \[傳回型別\]。|  
|**Custom**|插入於 \[方法名稱\] 清單中選取之方法的 Stub 實作。  對於自訂方法型別，您可以提供您自訂的傳回型別，或從 \[傳回型別\] 清單上選取一個。|  
  
 **內部名稱**  
 只有加入至 MFC 分配介面的自訂方法可以使用。  設定用於分派對應 \(Dispatch Map\)、標頭檔 \(.h\) 和實作檔 \(.cpp\) 的名稱。  依照預設，這個名稱和 \[方法名稱\] 相同。  如果您使用 MFC 分配介面，或者如果您將自訂方法加入至 MFC ActiveX 控制項分配介面上，則您可以變更該方法名稱。  
  
|介面型別|描述|  
|----------|--------|  
|ATL 雙重介面、自訂介面和本機自訂介面|無法使用|  
|MFC 分配介面|預設為方法名稱，  您可編輯此內部名稱。|  
|MFC ActiveX 控制項分配介面|您只能設定自訂方法的內部名稱，  內建方法並不使用內部名稱。|  
  
 **參數屬性**  
 設定在 \[參數名稱\] 中指定之參數的任何其他屬性。  
  
|參數屬性|描述|允許的組合|  
|----------|--------|-----------|  
|**In**|表示參數從呼叫程序傳遞至被呼叫程序。|只限 **in**<br /><br /> **in** 和 **out**|  
|**Out**|表示指標參數從被呼叫的程序傳回到呼叫程序 \(從伺服器到用戶端\)。|只限 **out**<br /><br /> **in** 和 **out**<br /><br /> **out** 和 **retval**|  
|**Retval**|表示參數接收成員的傳回值。|**retval** 和 out|  
  
 **參數型別**  
 設定參數的資料型別。  從清單中選取型別。  
  
 **參數名稱**  
 設定透過方法傳遞的參數名稱。  輸入名稱之後，必須按一下 \[加入\] 以將它加入至會透過方法傳遞的參數清單上。  如果沒有提供參數名稱，則精靈會忽略任一個參數屬性 \(僅 ATL\) 或 \[參數型別\] 的選取項目。  
  
 按一下 \[加入\] 之後，參數名稱會出現在 \[**參數清單**\] 中。  
  
 **注意：**如果您在輸入參數名稱後先按一下 \[完成\]，再按一下 \[加入\]，則參數不會加入至方法中。  而必須尋找該方法，然後手動插入參數。  
  
 **加入**  
 將您在 \[參數名稱\] 中指定的參數與其型別和參數屬性加入至 \[**參數清單**\]。  您必須按一下 \[加入\] 才能將參數加入清單。  
  
 **Remove**  
 將您在 \[參數清單\] 中選取的參數從清單中移除。  
  
 **參數清單**  
 顯示方法目前已加入的所有參數、修飾詞 \(Modifier\) 和型別。  加入參數時，精靈會更新 \[**參數清單**\] 以顯示每一個參數、參數的修飾詞和型別。  
  
## 請參閱  
 [加入方法](../ide/adding-a-method-visual-cpp.md)   
 [IDL 屬性、加入方法精靈](../ide/idl-attributes-add-method-wizard.md)