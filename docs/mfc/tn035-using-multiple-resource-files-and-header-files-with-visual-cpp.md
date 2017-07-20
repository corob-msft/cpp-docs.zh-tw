---
title: "TN035：在 Visual C++ 中使用多個資源檔和標頭檔 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.resources"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "資源檔，多個"
  - "TN035"
ms.assetid: 1f08ce5e-a912-44cc-ac56-7dd93ad73fb6
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN035：在 Visual C++ 中使用多個資源檔和標頭檔
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  下列技術提示自其納入線上文件以來，未曾更新。  因此，有些程序和主題可能已過期或不正確。  如需最新資訊，建議您在線上文件索引中搜尋相關的主題。  
  
 本提示說明 Visual C\+\+ 資源編輯器如何支援在單一專案內共用或跨多項專案共用的多個資源檔和標頭檔，以及如何善加運用該支援。  這份提示將回答下列問題：  
  
-   什麼時候最好要將專案分割成多個資源檔和\/或標頭檔，以及如何這麼做？  
  
-   如何在兩個 .RC 檔之間共用通用 .H 標頭檔？  
  
-   如何將專案資源分割成多個 .RC 檔？  
  
-   您 \(和工具\) 如何管理 .RC、.CPP 與 .H 檔案之間的組建相依性？  
  
 請注意，如果將額外的資源檔加入至專案，ClassWizard 就無法辨識所加入之檔案中的資源。  
  
 這份提示是定型解答，針對上述問題回應的內容如下：  
  
-   **Overview of How Visual C\+\+ Manages Resource Files and Header Files**提供 Visual C\+\+ 的 \[Resource Set Includes\] 命令如何讓您在同一個專案中使用多個資源檔和標頭檔的概觀。  
  
-   **Analysis of AppWizard\-created .RC and .H Files**著眼於 AppWizard 建立的應用程式所使用的多個資源檔及標頭檔。  這些檔案可以在您需要將其他資源檔和標頭檔加入至專案時，做為這些檔案的良好典範。  
  
-   **Including Additional Header Files**說明您可能需要加入多個標頭檔的地方，並提供如何這麼做的詳細資訊。  
  
-   **Sharing a Header File Between Two .RC Files**告訴您如何在不同專案 \(或是相同專案\) 中的多個 .RC 檔之間共用一個標頭檔。  
  
-   **Using Multiple Resource Files in the Same Project**說明您可能需要將專案分解成多個 .RC 檔的地方，並提供如何這麼做的詳細資訊。  
  
-   **Enforcement of Non\-Editable Visual C\+\+ Files**說明如何確認 Visual C\+\+ 不會編輯自訂資源且不會無意中重新設定其格式。  
  
-   **Managing Symbols Shared by Multiple Visual C\+\+\-Edited .RC Files**說明如何跨多個 .RC 檔共用相同的符號，以及如何避免指派重複的 ID 數值。  
  
-   **Managing Dependencies Between .RC, .CPP, and .H Files**說明 Visual C\+\+ 如何避免對相依於資源符號檔的 .CPP 檔案進行不必要的重新編譯。  
  
-   **How Visual C\+\+ Manages Set Includes Information**提供技術詳細資料，說明 Visual C\+\+ 如何追蹤多個 \(巢狀\) .RC 檔以及 .RC 檔藉由 \#include 所包含的多個標頭檔。  
  
 **Visual C\+\+ 如何管理資源檔和標頭檔的概觀**  
  
 Visual C\+\+ 將單一 .RC 資源檔和對應的 .H 標頭檔當做緊密結合的一組檔案來管理。  當您編輯和儲存 .RC 檔中的資源時，會間接編輯和儲存對應 .H 檔案中的符號。  雖然您可以同時開啟和編輯多個 .RC 檔 \(使用 Visual C\+\+ 的 MDI 使用者介面\)，但對任何指定 .RC 檔來說，您間接編輯的就恰好只有一個對應的標頭檔。  
  
 **符號標頭檔**  
  
 根據預設，不論資源檔的名稱為何 \(例如 MYAPP.RC\)，Visual C\+\+ 永遠將對應的標頭檔命名為 RESOURCE.H。  在 Visual C\+\+ 中，您可以使用 \[**View**\] 功能表的 \[**Resource Includes**\] 命令，透過更新 \[**Set Includes**\] 對話方塊中的符號標頭檔來變更這個標頭檔的名稱。  
  
 **唯讀符號指示詞**  
  
 雖然 Visual C\+\+ 對於任何指定的 .RC 檔都只會編輯一個標頭檔，但是 Visual C\+\+ 也支援其他唯讀標頭檔中所定義之符號的參考。  在 Visual C\+\+ 中，您可以使用 \[**View**\] 功能表的 \[**Resource Includes**\] 命令，將任何數目的其他唯讀標頭檔指定為唯讀符號指示詞。  「唯讀」限制表示，當您在 .RC 檔中加入新資源時，您可以使用唯讀標頭檔中定義的符號，但若刪除資源，符號在唯讀標頭檔中仍然維持已定義狀態。  您無法變更指派給唯讀符號的數值。  
  
 **編譯時期指示詞**  
  
 Visual C\+\+ 也支援巢狀資源檔，也就是藉由 \#include 將一個 .RC 檔包含在另一個資源檔中。  使用 Visual C\+\+ 編輯指定的 .RC 檔時，以 \#include 所包含之檔案中的任何資源都不是可見的。  但是當您編譯 .RC 檔時，同樣會編譯 \#include 所包含的檔案。  在 Visual C\+\+ 中，您可以使用 \[**View**\] 功能表的 \[**Resource Includes**\] 命令，將任何數目以 \#include 包含的 .RC 檔指定為編譯時期指示詞。  
  
 如果您讓 Visual C\+\+ 讀入的 .RC 檔，透過 \#include 包含了*未*指定為編譯時期指示詞的另一個 .RC 檔時，請注意會發生什麼情況。  當您在 Visual C\+\+ 中加入您先前使用文字編輯器手動維護的 .RC 檔時，這種情況就可能出現。  Visual C\+\+ 讀取 \#include 包含的 .RC 檔時，會將 \#include 的資源合併至父代 .RC 檔中。  當您儲存父代 .RC 檔時，實際上會以 \#include 的資源來取代 \#include 陳述式。  如果您不願意發生這種合併，就應該在 Visual C\+\+ 讀入父代 .RC 檔*之前*，從其中移除 \#include 陳述式，然後再使用 Visual C\+\+，將相同的 \#include 陳述式重新加入做為編譯時期指示詞。  
  
 Visual C\+\+ 會在 \#include 指示詞中 \(*以及*在 TEXTINCLUDE 資源中\) 儲存 .RC 檔的上述三種 Set Includes 資訊 \(符號標頭檔、唯讀符號指示詞和編譯時期指示詞\)。  TEXTINCLUDE 資源是您通常不需要處理的實作詳細資料，這會在[Visual C\+\+ 如何管理 Set Includes 資訊](#_mfcnotes_tn035_set_includes)中說明。  
  
 **分析 AppWizard 建立的 .RC 和 .H 檔案**  
  
 檢查 AppWizard 產生的應用程式程式碼可讓您深入了解 Visual C\+\+ 如何管理多個資源檔和標頭檔。  下面檢查的程式碼是摘錄自 AppWizard 使用預設選項所產生的 MYAPP 應用程式。  
  
 AppWizard 建立的應用程式會使用多個資源檔和多個標頭檔，如下圖摘要所示：  
  
```  
RESOURCE.H     AFXRES.H                      
       \       /                                
        \     /                                  
       MYAPP.RC                                 
           |                                  
           |                                
     RES\MYAPP.RC2    
     AFXRES.RC                     
     AFXPRINT.RC                   
```  
  
 您可以使用 Visual C\+\+ \[File\/Set Includes\] 命令，檢視這些檔案關聯性。  
  
 MYAPP.RC  
 您使用 Visual C\+\+ 編輯的應用程式資源檔。  
  
 RESOURCE.H 是應用程式專用的標頭檔。  AppWizard 永遠將其命名為 RESOURCE.H，這與 Visual C\+\+ 的標頭檔預設命名方式一致。  標頭檔的 \#include 是資源檔 \(MYAPP.RC\) 中的第一個陳述式：  
  
```  
//Microsoft Visual C++ generated resource script  
//  
#include "resource.h"  
```  
  
 RES\\MYAPP.RC2  
 包含 Visual C\+\+ 不會加以編輯、但會包含在最終編譯後 .EXE 檔案中的資源。  由於 Visual C\+\+ 可以編輯任何標準資源，包括版本資源 \(這個版本中的新功能\)，因此 AppWizard 預設不會建立此類資源。  AppWizard 會產生空白檔案，以備您想要自行在這個檔案中加入自訂格式的資源。  
  
 如果您使用自訂格式的資源，可以使用 Visual C\+\+ 文字編輯器，將這些資源加入至 RES\\MYAPP.RC2 並進行編輯。  
  
 AFXRES.RC 和 AFXPRINT.RC 包含 Framework 某些功能所需的標準資源。  就像 RES\\MYAPP.RC2，這兩個 Framework 提供的資源檔以 \#include 包含在 MYAPP.RC 結尾，並且是在 \[Set Includes\] 對話方塊的編譯時期指示詞中指定。  因此，當您在 Visual C\+\+ 中編輯 MYAPP.RC 時，這些 Framework 資源無法直接加以檢視或編輯，但還是會編譯至應用程式的二進位 .RES 檔案與最終 .EXE 檔案。  如需標準 Framework 資源的詳細資訊 \(包括進行修改的程序\)，請參閱[技術提示 23](../mfc/tn023-standard-mfc-resources.md)。  
  
 AFXRES.H 會定義標準符號，例如 Framework 所使用 \(特別是用在 AFXRES.RC 中\) 的 `ID_FILE_NEW`。  AFXRES.H 也會以 \#include 包含 WINRES.H，後者含有 Visual C\+\+ 產生之 .RC 檔以及 AFXRES.RC 所需的 WINDOWS.H 子集。  AFXRES.H 中定義的符號可供您在編輯應用程式資源檔 \(MYAPP.RC\) 時使用。  例如，`ID_FILE_NEW` 是用於 MYAPP.RC 功能表資源中的 \[開新檔案\] 功能表項目。  您無法變更或刪除這些 Framework 定義的符號。  
  
 **包含其他標頭檔**  
  
 AppWizard 建立的應用程式只會包含兩個標頭檔：RESOURCE.H 和 AFXRES.H。  只有 RESOURCE.H 是應用程式專用的。  您可能需要在下列情況中包含其他唯讀標頭檔：  
  
 標頭檔是由外部來源提供，或者您想要在多個專案之間或相同專案的多個組件之間共用標頭檔。  
  
 標頭檔含有您不希望 Visual C\+\+ 在儲存檔案時加以變更或篩除的格式設定和註解。  例如，您或許想要保留使用符號算術的 \#define：  
  
```  
#define RED 0  
#define BLUE 1  
#define GREEN 2  
#define ID_COLOR_BUTTON 1001  
#define ID_RED_BUTTON (ID_COLOR_BUTTON + RED)  
#define ID_BLUE_BUTTON (ID_COLOR_BUTTON + BLUE)  
#define ID_GREEN_BUTTON (ID_COLOR_BUTTON + GREEN)  
```  
  
 您可以包含其他唯讀標頭檔，做法是使用 \[**Resource Includes**\] 命令，將 \#include 陳述式指定為第二個唯讀符號指示詞，如下所示：  
  
```  
#include "afxres.h"  
#include "second.h"  
```  
  
 新的檔案關聯性圖表，現在看起來像這樣：  
  
```  
               AFXRES.H         
RESOURCE.H     SECOND.H                      
      \       /                                
       \     /                                  
      MYAPP.RC     
          |                                  
          |                                
    RES\MYAPP.RC2    
    AFXRES.RC                     
    AFXPRINT.RC                   
```  
  
 **在兩個 .RC 檔案之間共用標頭檔**  
  
 您可能會想要在不同專案 \(或可能相同專案\) 中的兩個 .RC 檔之間共用標頭檔。  若要這麼做，只需將上述「唯讀指示詞」技術套用至這兩個 .RC 檔即可。  在兩個 .RC 檔分屬不同應用程式 \(不同專案\) 的情況下，結果如下圖所示：  
  
```  
     RESOURCE.H   AFXRES.H   RESOURCE.H    
    (for MYAPP1)  SECOND.H   (for MYAPP2)               
          \       /     \       /             
           \     /       \     /               
          MYAPP1.RC      MYAPP2.RC                   
           /    \        /     \                     
          /      \      /       \              
RES\MYAPP1.RC2  AFXRES.RC     RES\MYAPP2.RC2                
                AFXPRINT.RC                   
```  
  
 以下將討論第二種在相同應用程式 \(專案\) 中由兩個 .RC 檔案共用標頭檔的情況。  
  
 **在相同專案中使用多個資源檔**  
  
 Visual C\+\+ 和資源編譯器透過 .RC 檔中另一個資源檔的 \#include 支援相同專案中的多個 .RC 檔。  這會允許多重巢狀。  有各種原因需要將專案的資源分割成多個 .RC 檔：  
  
-   如果將資源分割成多個 .RC 檔，管理多個專案小組成員之間的大量資源會更為容易。  如果使用原始檔控制管理套件進行檔案簽出和變更簽入，將資源分割成多個 .RC 檔可讓您對管理資源的變更掌握更細微的控制。  
  
-   如果資源的某些部分需要使用前置處理器指示詞 \(例如 \#ifdef、\#endif 和 \#define\)，您必須將這些部分放在會由資源編譯器編譯的唯讀資源中隔離。  
  
-   在 Visual C\+\+ 中，載入和儲存一組個別 .RC 檔會比載入和儲存一個複合 .RC 檔還要快速。  
  
-   如果您想要使用文字編輯器以人類看得懂的格式維護資源，就必須將此資源保留在 Visual C\+\+ 會編輯的資源檔以外的不同 .RC 檔中。  
  
-   如果您需要以其他特定資料編輯器可解譯的二進位或文字格式來保留使用者定義的資源，那麼就必須在個別 .RC 檔中保留此資源，這樣 Visual C\+\+ 才不會將格式變更為十六進位資料。  MFC 進階概念範例 [SPEAKN](../top/visual-cpp-samples.md) 中的 .WAV \(聲音\) 檔案資源即是很好的例子。  
  
 您可以在 \[Set Includes\] 對話方塊中，使用 \#include 將 SECOND.RC 包含在編譯時期指示詞中：  
  
```  
#include "res\myapp.rc2"  // non-Visual C++ edited resources  
#include "second.rc"  // THE SECOND .RC FILE  
  
#include "afxres.rc"  // Standard components  
#include "afxprint.rc"  // printing/print preview resources  
```  
  
 結果如下圖所示：  
  
```  
RESOURCE.H     AFXRES.H                      
       \       /                                
        \     /                                  
       MYAPP.RC  
           |                                  
           |                                
     RES\MYAPP.RC2  
     SECOND.RC    
     AFXRES.RC                     
     AFXPRINT.RC                   
```  
  
 您可以使用編譯時期指示詞，將 Visual C\+\+ 可編輯與不可編輯的資源組織在多個 .RC 檔案，其中「主要」MYAPP.RC 除了藉由 \#include 包含其他 .RC 檔外，就什麼事也不做。  如果您要使用 Visual C\+\+ 專案 .MAK 檔案，則必須在專案中包含「主要」.RC 檔，這樣才能讓所有 \#include 的資源與您的應用程式一起編譯。  
  
 **強制設定不可編輯的 Visual C\+\+ 檔案**  
  
 例如，AppWizard 建立的 RES\\MYAPP.RC2 檔案即是包含您*不*希望 Visual C\+\+ 意外讀入，又接著加以寫出而遺失格式設定資訊之資源的檔案。  若要避免這種情況，請將下列程式碼行放在 RES\\MYAPP.RC2 檔案的開頭：  
  
```  
#ifdef APSTUDIO_INVOKED  
    #error this file is not editable by Visual C++  
#endif //APSTUDIO_INVOKED  
```  
  
 Visual C\+\+ 編譯 .RC 檔時，會定義 **APSTUDIO\_INVOKED** 和 **RC\_INVOKED**。  如果 AppWizard 建立的檔案結構損毀，而且 Visual C\+\+ 讀取了上述 \#error 行，就會報告嚴重錯誤並中止 .RC 檔案讀取。  
  
 **管理 Visual C\+\+ 編輯的多個 .RC 檔案所共用的符號**  
  
 當您將資源分割成多個要在 Visual C\+\+ 中個別編輯的 .RC 檔時，會引發兩個問題：  
  
-   您可能會想要跨多個 .RC 檔共用相同的符號。  
  
-   您需要協助 Visual C\+\+ 避免將相同的 ID 數值指派給不同資源 \(符號\)。  
  
 下圖說明處理第一個問題的 .RC 和 .H 檔案的組織：  
  
```  
              MYAPP.RC  
             /         \  
            /           \  
MYSTRS.H   / MYSHARED.H  \  MYMENUS.H  
     \    /    /      \   \    \  
      \  /    /        \   \    \  
   MYSTRS.RC           MYMENUS.RC  
```  
  
 在這個範例中，字串資源保留在一個資源檔 MYSTRS.RC，而功能表保留在另一個資源檔 MYMENUS.RC。  有些符號 \(例如命令的符號\) 可能需要在兩個檔案之間共用。  例如，ID\_TOOLS\_SPELL 可以是 \[工具\] 功能表中的 \[拼字\] 項目，也可以是應用程式主視窗狀態列框架所顯示之命令提示字元的字串 ID。  
  
 ID\_TOOLS\_SPELL 符號是保留在共用標頭檔 MYSHARED.H 中。  您可以使用文字編輯器手動維護這個共用標頭檔，Visual C\+\+ 無法直接進行編輯。  在兩個資源檔 MYSTRS.RC 和 MYMENUS.RC 中，您可以使用 \[**Resource Includes**\] 命令，將 \#include MYSHARED.H 指定於 MYAPP.RC 的唯讀指示詞，如之前所述。  
  
 嘗試使用符號識別任何資源之前，您最好預先準備將會共用的符號。  將這個符號加入至標頭檔，如果您還沒有使用 \#include 在 .RC 檔的唯讀指示詞中包含共用標頭檔，請在使用符號前這麼做。  如果您未以這種方式預先準備共用符號，那麼就必須手動 \(使用文字編輯器\) 將符號的 \#define 陳述式，\(比方說\) 在符號用於 MYSTRS.RC 之前從 MYMENUS.H 移至 MYSHARED.H。  
  
 當您管理多個 .RC 檔中的符號時，也必須協助 Visual C\+\+ 避免將相同的 ID 數值指派給不同資源 \(符號\)。  對於任何指定的 .RC 檔，Visual C\+\+ 會自動累加指派每個 ID 定義域 \(總共四個\) 中的 ID。  在編輯工作階段之間，Visual C\+\+ 會記錄上次在 .RC 檔符號標頭檔的每個定義域中指派的 ID。  以下說明 APS\_NEXT 值對空白 \(新增\) .RC 檔的意義：  
  
```  
#define _APS_NEXT_RESOURCE_VALUE  101  
#define _APS_NEXT_COMMAND_VALUE   40001  
#define _APS_NEXT_CONTROL_VALUE   1000  
#define _APS_NEXT_SYMED_VALUE     101  
```  
  
 **\_APS\_NEXT\_RESOURCE\_VALUE** 是要用於對話方塊、功能表等資源的下一個符號值。  資源符號值的有效範圍是 1 至 0x6FFF。  
  
 **\_APS\_NEXT\_COMMAND\_VALUE** 是要用於命令識別的下一個符號值。  命令符號值的有效範圍是 0x8000 至 0xDFFF。  
  
 **\_APS\_NEXT\_CONTROL\_VALUE** 是要用於對話方塊控制項的下一個符號值。  對話方塊控制項符號值的有效範圍是 8 至 0xDFFF。  
  
 **\_APS\_NEXT\_SYMED\_VALUE** 是您使用符號瀏覽器的 \[New\] 命令手動指派符號值時，將會發行的下一個符號值。  
  
 建立新的 .RC 檔時，Visual C\+\+ 一開始會使用比最低合法值稍微高的值。  AppWizard 也會將這些值初始化為一些較適合 MFC 應用程式的值。  如需 ID 值範圍的詳細資訊，請參閱[技術提示 20](../mfc/tn020-id-naming-and-numbering-conventions.md)。  
  
 現在，每當您建立新的資源檔時，即使是在同一個專案中，Visual C\+\+ 都會定義相同的 **\_APS\_NEXT\_** 值。  這表示，如果您在兩個不同 .RC 檔中加入 \(舉例說\) 多個對話方塊，很有可能會將相同的 \#define 值指派給不同的對話方塊。  例如，第一個 .RC 檔的 IDD\_MY\_DLG1 和第二個 .RC 檔的 IDD\_MY\_DLG2 可能都有相同的指派數字 101。  
  
 若要避免這種情況，您應該在不同 .RC 檔案中分別為每個 ID 定義域 \(總共四個\) 各自保留不同的數值範圍。  您可以在開始加入資源`之前`，透過手動更新每個 .RC 檔的 **\_APS\_NEXT** 值來這麼做。  例如，如果第一個 .RC 檔使用預設 **\_APS\_NEXT** 值，那麼您可能會想要指派下列 **\_APS\_NEXT** 值給第二個 .RC 檔：  
  
```  
#define _APS_NEXT_RESOURCE_VALUE  2000  
#define _APS_NEXT_COMMAND_VALUE   42000  
#define _APS_NEXT_CONTROL_VALUE   2000  
#define _APS_NEXT_SYMED_VALUE     2000  
```  
  
 當然，Visual C\+\+ 仍舊可能在第一個 .RC 檔中指派這麼多的 ID，使得這些數值開始與第二個 .RC 檔保留的那些數值重疊。  您應該保留足夠大的範圍，讓這種情況就不會發生。  
  
 **管理 .RC、.CPP 和 .H 檔案之間的相依性**  
  
 Visual C\+\+ 儲存 .RC 檔時，也會將符號的變更儲存到對應的 RESOURCE.H 檔案。  在 .RC 檔中參考的資源的任何 .CPP 檔案通常都必須從專案的主要標頭檔中，以 \#include 包含 RESOURCE.H 檔案。  由於開發環境的內部專案管理會掃描原始程式檔的標頭相依性，這會產生不必要的副作用。  每當您在 Visual C\+\+ 中加入新符號時，都必須重新編譯所有藉由 \#include 包含 RESOURCE.H 的 .CPP 檔案。  
  
 Visual C\+\+ 會加入下列註解做為 RESOURCE.H 檔案的第一行，以避開對 RESOURCE.H 的相依性：  
  
```  
//{{NO_DEPENDENCIES}}  
```  
  
 開發環境會以忽略 RESOURCE.H 的變更來解譯此註解，這樣就不需要重新編譯相依 .CPP 檔案。  
  
 Visual C\+\+ 永遠會在儲存檔案時，將 \/\/{{NO\_DEPENDENCIES}} 註解行加入至 .RC 檔。  在某些情況下，避開 RESOURCE.H 的組建相依性可能導致連結時偵測不到執行階段錯誤。  例如，當您使用符號瀏覽器變更指派給資源符號的數值時，如果沒有重新編譯參考資源的 .CPP 檔案，就無法在應用程式執行階段正確找到和載入資源。  在這類情況下，您應該明確地重新編譯已知道會受到 RESOURCE.H 中符號變更影響的任何 .CPP 檔案，或是選取 \[**Rebuild All**\]。  如果您需要經常變更特定資源群組的符號值，或許會發覺將這些符號另外建立成不同的唯讀標頭檔，更方便且更安全，如之前[包含其他標頭檔](#_mfcnotes_tn035_including)一節中所述。  
  
 **Visual C\+\+ 如何管理 Set Includes 資訊**  
  
 如前所述，\[File\] 功能表 \[Set Includes\] 命令可讓您指定三種類型的資訊：  
  
-   符號標頭檔  
  
-   唯讀符號指示詞  
  
-   編譯時期指示詞  
  
 以下將說明 Visual C\+\+ 如何在 .RC 檔案中維護這個資訊。  您不需要此項資訊也可以使用 Visual C\+\+，但是這可以增進您的理解，讓自己有更多的把握使用 \[Set Includes\] 功能。  
  
 上述三種類型的 Set Includes 資訊都個別以兩種形式儲存於 .RC 檔：\(1\) 為 \#include 或其他可由資源編譯器解譯的指示詞，以及 \(2\) 為只能由 Visual C\+\+ 解譯的特殊 TEXTINCLUDE 資源。  
  
 TEXTINCLUDE 資源的用途是安全地以立即可供 Visual C\+\+ 顯示在 \[**Set Includes**\] 對話方塊的形式儲存的 Set Includes 資訊。  TEXTINCLUDE 是 Visual C\+\+ 定義的*資源類型*。  Visual C\+\+ 可以辨認資源識別碼為 1、2 和 3 的三個特定 TEXTINCLUDE 資源：  
  
|TEXTINCLUDE 資源 ID|Set Includes 資訊的類型|  
|-----------------------|------------------------|  
|1|符號標頭檔|  
|2|唯讀符號指示詞|  
|3|編譯時期指示詞|  
  
 AppWizard 建立的預設 MYAPP.RC 和 RESOURCE.H 檔案會示例說明三種 Set Includes 資訊中的每一個類型，如下所述。  BEGIN 和 END 區塊之間的額外 \\0 和 "" 語彙基元是基於 RC 語法的需求，分別用來指定以零結尾的字串和雙引號字元。  
  
## 符號標頭檔  
 資源編譯器所解譯的符號標頭檔資訊的形式只是簡單的 \#include 陳述式：  
  
```  
#include "resource.h"  
```  
  
 對應的 TEXTINCLUDE 資源為：  
  
```  
1 TEXTINCLUDE DISCARDABLE  
BEGIN  
   "resource.h\0"  
END  
```  
  
## 唯讀符號指示詞  
 唯讀符號指示詞是以資源編譯器可解譯的下列形式包含在 MYAPP.RC 頂端：  
  
```  
#include "afxres.h"  
```  
  
 對應的 TEXTINCLUDE 資源為：  
  
```  
2 TEXTINCLUDE DISCARDABLE  
BEGIN  
   "#include ""afxres.h""\r\n"  
   "\0"  
END  
```  
  
## 編譯時期指示詞  
 編譯時期指示詞是以資源編譯器可解譯的下列形式包含在 MYAPP.RC 結尾：  
  
```  
#ifndef APSTUDIO_INVOKED  
///////////////////////  
//  
// From TEXTINCLUDE 3  
//  
#include "res\myapp.rc2"  // non-Visual C++ edited resources  
  
#include "afxres.rc"  // Standard components  
#include "afxprint.rc"  // printing/print preview resources  
#endif  // not APSTUDIO_INVOKED  
```  
  
 \#ifndef APSTUDIO\_INVOKED 指示詞會指示 Visual C\+\+ 略過編譯時期指示詞。  
  
 對應的 TEXTINCLUDE 資源為：  
  
```  
3 TEXTINCLUDE DISCARDABLE  
BEGIN  
"#include ""res\myapp.rc2""  // non-Visual C++ edited resources\r\n"  
"\r\n"  
"#include ""afxres.rc""  // Standard components\r\n"  
"#include ""afxprint.rc""  // printing/print preview resources\r\n"  
"\0"  
END  
```  
  
## 請參閱  
 [依編號顯示的技術提示](../mfc/technical-notes-by-number.md)   
 [依分類區分的技術提示](../mfc/technical-notes-by-category.md)