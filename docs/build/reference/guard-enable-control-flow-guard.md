---
title: "/guard (啟用控制流程防護) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/guard"
  - "VC.Project.VCCLCompilerTool.ControlFlowGuard"
dev_langs: 
  - "C++"
ms.assetid: be495323-f59f-4cf3-a6b6-8ee69e6a19dd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# /guard (啟用控制流程防護)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

啟用控制流程防護安全性檢查的編譯器產生。  
  
## 語法  
  
```  
/guard:cf[-]  
```  
  
## 備註  
 **\/guard:cf** 選項讓編譯器在編譯階段分析間接呼叫目標的控制流程，然後插入程式碼以在執行階段確認目標。 根據預設，**\/guard:cf** 關閉且必須明確啟用。 若要明確停用此選項，請使用 **\/guard:cf\-**。  
  
 當已指定 **\/guard:cf** 控制流程防護 \(CFG\) 選項時，編譯器和連結器會插入額外的執行階段安全性檢查，以偵測入侵您程式碼的嘗試。 在編譯和連結期間，程式碼中的所有間接呼叫都會經過分析，以尋找程式碼正確執行時所能到達的每個位置。 這項資訊會儲存在二進位編碼檔案標頭中的額外結構。 編譯器也會在程式碼的每個間接呼叫之前注入檢查，以確保目標是其中一個已驗證的位置。 如果在 CFG 感知作業系統上執行階段的檢查失敗，作業系統會關閉該程式。  
  
 常見的軟體攻擊，會利用在處理極端或未預期輸入方面的錯誤。 精心製作的應用程式輸入可能會覆寫包含可執行程式碼之指標的位置。 這可用來將控制流程重新導向至攻擊者所控制的程式碼。 CFG 執行階段檢查無法修正可執行檔中的資料損毀 Bug。 反而是讓攻擊者更難利用它們執行任意程式碼。 CFG 是一種緩和工具，可防止呼叫程式碼中非函式進入點的位置。 其方式與資料執行防止 \(DEP\)、[\/GS](../../build/reference/gs-buffer-security-check.md) 堆疊檢查，以及 [\/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) 與 [\/HIGHENTROPYVA](../../build/reference/highentropyva-support-64-bit-aslr.md) 位址空間配置隨機載入 \(ASLR\) 降低您的程式碼成為攻擊向量的機會類似。  
  
 **\/guard:cf** 選項必須同時傳遞給編譯器和連結器，以建置使用 CFG 入侵防護技術的程式碼。 如果您的二進位檔是使用單一 `cl` 命令建置，則編譯器會將選項傳遞給連結器。 如果您分別進行編譯和連結，則必須同時在編譯器和連結器命令設定選項。 \/DYNAMICBASE 連結器選項也是必要的。 若要確認您的二進位檔有 CFG 資料，請使用 `dumpbin /headers /loadconfig` 命令。 具有 CFG 功能的二進位檔在 EXE 或 DLL 的特性清單中會有`防護`，而防護旗標則包括 `CF 檢測`和 `FID 資料表存在`。  
  
 **\/guard:cf** 選項與 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) \(編輯後繼續偵錯資訊\) 或 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md) \(Common Language Runtime 編譯\) 不相容。  
  
 使用 **\/guard:cf** 編譯的程式碼可以連結到未使用該選項編譯的程式庫和物件檔案。 當同樣使用 **\/guard:cf** 選項連結，並在 CFG 感知的作業系統上執行時，只有此程式碼會具有 CFG 保護。 由於未使用該選項編譯的程式碼不會停止攻擊，我們建議您對所編譯的所有程式碼都使用此選項。 CFG 檢查有小量的執行階段成本，但編譯器分析會略過可證實為安全的間接跳躍點檢查，嘗試進行最佳化。  
  
### 在 Visual Studio 開發環境中設定這個編譯器選項  
  
1.  開啟專案的 \[屬性頁\] 對話方塊。 如需詳細資訊，請參閱[如何：開啟專案屬性頁](../../misc/how-to-open-project-property-pages.md)。  
  
2.  選取 \[組態屬性\]、\[C\/C\+\+\]、\[程式碼產生\]。  
  
3.  選取 \[控制流程防護\] 屬性。  
  
4.  在下拉式清單控制項中，選擇 \[是\] 啟用控制流程防護，或選擇 \[否\] 將其停用。  
  
## 請參閱  
 [編譯器選項](../../build/reference/compiler-options.md)   
 [設定編譯器選項](../../build/reference/setting-compiler-options.md)