---
title: "編譯器錯誤 C2200 到 C2299 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2202
- C2209
- C2210
- C2211
- C2214
- C2215
- C2221
- C2225
- C2230
- C2235
- C2237
- C2239
- C2240
- C2257
- C2260
- C2263
- C2265
- C2269
- C2278
- C2281
- C2282
- C2288
- C2291
- C2294
helpviewer_keywords:
- C2202
- C2209
- C2210
- C2211
- C2214
- C2215
- C2221
- C2225
- C2230
- C2235
- C2237
- C2239
- C2240
- C2257
- C2260
- C2263
- C2265
- C2269
- C2278
- C2281
- C2282
- C2288
- C2291
- C2294
dev_langs:
- C++
ms.assetid: 9b36d11b-9510-4390-96f1-0c9235124d14
caps.latest.revision: 13
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: d7d097b399d3681ef523d8787ecc38af472840f6
ms.openlocfilehash: f47a6fe23a8a0bf18f9c5c4399162d836667cab6
ms.contentlocale: zh-tw
ms.lasthandoff: 04/28/2017

---
# <a name="compiler-errors-c2200-through-c2299"></a>編譯器錯誤 C2200 到 C2299
這部分文件中的文章包含 Visual C++ 編譯器錯誤的子區段的相關資訊。 您可以在此存取資訊，或是在 Visual Studio 的 [ **輸出** ] 視窗，您可以選取錯誤代碼然後選擇 F1 鍵。  
  
> [!NOTE]
>  並非每個[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]錯誤會記載於 MSDN 中。 在許多情況下，診斷訊息會提供所有可用的資訊。 如果您認為錯誤訊息需要補充說明，請告訴我們。 您可以使用這個頁面上的回函表單或移至 Visual Studio 中的功能表列並選擇**協助**，**回報 Bug**，或您可以提出建議或 bug 報告上[Microsoft Connect](http://connect.microsoft.com/VisualStudio)。  
  
 您可能會發現其他協助的 MSDN 公共論壇上錯誤及警告。 [Visual c + + 語言](http://go.microsoft.com/fwlink/?LinkId=158195)論壇是關於問題及討論[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]語言語法和編譯器。 [Visual c + + 一般](http://go.microsoft.com/fwlink/?LinkId=158194)論壇是關於問題[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]其他論壇中沒有討論之。 您也可能會在找到關於錯誤和警告的說明[堆疊溢位](http://stackoverflow.com/)。  
  
|錯誤|訊息|  
|-----------|-------------|  
|[編譯器錯誤 C2200](compiler-error-c2200.md)|'*函式*': 已經定義函式|  
|[編譯器錯誤 C2201](compiler-error-c2201.md)|'*識別碼*': 必須具有外部連結以便匯出/匯入|  
|編譯器錯誤 C2202|'*函式*': 不是所有控制路徑都傳回值|  
|[編譯器錯誤 C2203](compiler-error-c2203.md)|不能使用 delete 運算子指定陣列的界限|  
|[編譯器錯誤 C2204](compiler-error-c2204.md)|'*類型*': 括號內找到類型的定義|  
|[編譯器錯誤 C2205](compiler-error-c2205.md)|'*識別碼*': 無法初始化 extern 變數具有區塊範圍|  
|[編譯器錯誤 C2206](compiler-error-c2206.md)|'*函式*': 函式定義不使用 typedef|  
|[編譯器錯誤 C2207](compiler-error-c2207.md)|'*成員*': 類別樣板的成員無法取得函式類型|  
|[編譯器錯誤 C2208](compiler-error-c2208.md)|'*類型*': 沒有使用這個型別定義的成員|  
|編譯器錯誤 C2209|'*識別碼*': 不能在建構函式宣告中使用別名|  
|編譯器錯誤 C2210|'*識別碼*': 封裝展開不能當做別名樣板中的未封裝參數的引數|  
|編譯器錯誤 C2211|Ref 類別，衍生自具有公用解構函式的 ref 類別中的非虛擬解構函式也必須是公用|  
|[編譯器錯誤 C2212](compiler-error-c2212.md)|'*識別碼*': __based 不提供函式指標|  
|[編譯器錯誤 C2213](compiler-error-c2213.md)|'*識別碼*': __based 的引數不合法|  
|編譯器錯誤 C2214|以 'void' 為基礎的指標需要使用 :>|  
|編譯器錯誤 C2215|'*關鍵字*' 不能使用 ' / /arch: SSE'|  
|[編譯器錯誤 C2216](compiler-error-c2216.md)|'*keyword1*'不能與'*keyword2*'|  
|[編譯器錯誤 C2217](compiler-error-c2217.md)|'*attribute1*'需要'*attribute2*'|  
|[編譯器錯誤 C2218](compiler-error-c2218.md)|'*calltype*' 不能使用 ' / /arch: IA32'|  
|[編譯器錯誤 C2219](compiler-error-c2219.md)|語法錯誤: 類型限定詞必須在 '*' 之後|  
|[編譯器錯誤 C2220](compiler-error-c2220.md)|將警告視為錯誤-沒有 '*filetype*' 產生的檔案|  
|編譯器錯誤 C2221|已過時。|  
|[編譯器錯誤 C2222](compiler-error-c2222.md)|未預期的類型 '*類型*': 必須是基底類別或成員|  
|[編譯器錯誤 C2223](compiler-error-c2223.md)|左邊的 '->*識別碼*' 必須指向結構/等位|  
|[編譯器錯誤 C2224](compiler-error-c2224.md)|左邊 '。*識別碼*' 必須擁有結構/等位型別|  
|編譯器錯誤 C2225|已過時。|  
|[編譯器錯誤 C2226](compiler-error-c2226.md)|語法錯誤︰ 未預期的類型 '*類型*'|  
|[編譯器錯誤 C2227](compiler-error-c2227.md)|左邊的 '->*識別碼*' 必須指向類別/結構/等位/泛型類型|  
|[編譯器錯誤 C2228](compiler-error-c2228.md)|左邊 '。*識別碼*' 必須有類別/結構/等位|  
|[編譯器錯誤 C2229](compiler-error-c2229.md)|類別/結構/等位 '*類型*' 具有不合法的大小為零的陣列|  
|編譯器錯誤 C2230|找不到模組 '*名稱*'|  
|[編譯器錯誤 C2231](compiler-error-c2231.md)|'.*識別碼*': 左運算元指向 ' 類別/結構/等位 '，請使用 '->'|  
|[編譯器錯誤 C2232](compiler-error-c2232.md)|'->*識別碼*': 左的運算元有' 類別/結構/等位 ' 類型，使用' '|  
|[編譯器錯誤 C2233](compiler-error-c2233.md)|'*識別碼*': 包含大小為零的陣列物件的陣列不合法|  
|[編譯器錯誤 C2234](compiler-error-c2234.md)|*識別項*': 參考的陣列不合法|  
|編譯器錯誤 C2235|已過時。|  
|[編譯器錯誤 C2236](compiler-error-c2236.md)|未預期的 token '*語彙基元*'。 您是否忘記 ';'？|  
|編譯器錯誤 C2237|多個模組宣告|  
|[編譯器錯誤 C2238](compiler-error-c2238.md)|未預期的語彙基元，上述 '*語彙基元*'|  
|編譯器錯誤 C2239|'*函式*': 嘗試刪除 __declspec （dllexport） 函式|  
|編譯器錯誤 C2240|已過時。|  
|[編譯器錯誤 C2241](compiler-error-c2241.md)|'*識別碼*': 成員存取受限制|  
|[編譯器錯誤 C2242](compiler-error-c2242.md)|typedef 名稱不可以跟隨類別/結構/等位|  
|[編譯器錯誤 C2243](compiler-error-c2243.md)|'*conversion_type*': 從'*type1*'to'*type2*' 存在，但無法存取|  
|[編譯器錯誤 C2244](compiler-error-c2244.md)|'*識別碼*': 無法比對現有的宣告的函式定義|  
|[編譯器錯誤 C2245](compiler-error-c2245.md)|不存在的成員函式 '*函式*' 指定為 friend （成員函式簽章不符合任何多載）|  
|[編譯器錯誤 C2246](compiler-error-c2246.md)|'*識別碼*': 在本機定義的類別中的不合法的靜態資料成員|  
|[編譯器錯誤 C2247](compiler-error-c2247.md)|'*識別碼*' 無法存取因為 '*class1*'使用'*規範*' 來繼承自'*class2*'|  
|[編譯器錯誤 C2248](compiler-error-c2248.md)|'*識別碼*': 無法存取*協助工具**成員*宣告中類別*類別*'|  
|[編譯器錯誤 C2249](compiler-error-c2249.md)|'*識別碼*': 沒有可存取路徑*協助工具**成員*虛擬基底中宣告'*類別*'|  
|[編譯器錯誤 C2250](compiler-error-c2250.md)|'*識別碼*': 模稜兩可的繼承*類別*::*成員*'|  
|[編譯器錯誤 C2251](compiler-error-c2251.md)|命名空間 '*命名空間*'沒有成員'*識別碼*'-您是指'*成員*' 嗎？|  
|[編譯器錯誤 C2252](compiler-error-c2252.md)|樣板的明確具現化只能在命名空間範圍進行|  
|[編譯器錯誤 C2253](compiler-error-c2253.md)|'*函式*': 純規範或抽象覆寫規範只適用於虛擬函式|  
|[編譯器錯誤 C2254](compiler-error-c2254.md)|'*函式*': 純規範或抽象覆寫規範不允許在 friend 函式|  
|[編譯器錯誤 C2255](compiler-error-c2255.md)|'*元素*': 不允許在類別定義之外|  
|[編譯器錯誤 C2256](compiler-error-c2256.md)|上的 friend 規範不合法使用 '*函式*'|  
|編譯器錯誤 C2257|'*規範*': 尾端傳回類型上不允許規範|  
|[編譯器錯誤 C2258](compiler-error-c2258.md)|不合法的純虛擬函式語法，必須是 '= 0'|  
|[編譯器錯誤 C2259](compiler-error-c2259.md)|'*類別*': 無法具現化抽象類別|  
|編譯器錯誤 C2260|'*規範*': 無效的 InternalsVisibleToAttribute friend 組件規範|  
|[編譯器錯誤 C2261](compiler-error-c2261.md)|'*字串*': 組件參考無效，無法解析|  
|[編譯器錯誤 C2262](compiler-error-c2262.md)|'*規範*': InternalsVisibleTo 宣告不能指定版本、 文化特性或處理器架構|  
|編譯器錯誤 C2263|已過時。|  
|[編譯器錯誤 C2264](compiler-error-c2264.md)|'*函式*': 函式定義或宣告中的錯誤; 未呼叫函式|  
|編譯器錯誤 C2265|已過時。|  
|[編譯器錯誤 C2266](compiler-error-c2266.md)|'*識別碼*': 參考至非常數界限的陣列不合法|  
|[編譯器錯誤 C2267](compiler-error-c2267.md)|'*函式*': 具有區塊範圍的靜態函式不合法|  
|[編譯器錯誤 C2268](compiler-error-c2268.md)|'*函式*' 是編譯器預先定義的程式庫 helper。 以 /GL 不支援程式庫協助程式編譯目的檔 '*filename*' /gl|  
|編譯器錯誤 C2269|無法建立指標或參考 （需要成員指標） 為限定的函式類型|  
|[編譯器錯誤 C2270](compiler-error-c2270.md)|'*函式*': 非成員函式不允許修飾詞|  
|[編譯器錯誤 C2271](compiler-error-c2271.md)|'*函式*': 新增/刪除不能有型式清單修飾詞|  
|[編譯器錯誤 C2272](compiler-error-c2272.md)|'*函式*': 靜態成員函式不允許修飾詞|  
|[編譯器錯誤 C2273](compiler-error-c2273.md)|'*類型*': 當做 '->' 運算子的右邊不合法|  
|[編譯器錯誤 C2274](compiler-error-c2274.md)|'*類型*': 當做的右邊不合法 '。' 運算子|  
|[編譯器錯誤 C2275](compiler-error-c2275.md)|'*類型*': 不合法使用這個型別做為運算式|  
|[編譯器錯誤 C2276](compiler-error-c2276.md)|'*運算子*': 界限的成員函式運算式中不合法的操作|  
|[編譯器錯誤 C2277](compiler-error-c2277.md)|'*函式*': 無法取得此成員函式的位址|  
|編譯器錯誤 C2278|已過時。|  
|[編譯器錯誤 C2279](compiler-error-c2279.md)|例外狀況規格不能出現在 typedef 宣告中|  
|[編譯器錯誤 C2280](compiler-error-c2280.md)|'*類別*::*函式*': 嘗試參考已刪除的函式|  
|編譯器錯誤 C2281|'*類別*::*函式*': 只能在第一個宣告上刪除函式|  
|編譯器錯誤 C2282|'*function1*'無法覆寫'*function2*'|  
|[編譯器錯誤 C2283](compiler-error-c2283.md)|'*識別碼*': 純規範或抽象覆寫規範不可使用未命名的類別結構|  
|編譯器錯誤 C2284|'*函式*': 內建函數的引數不合法參數*數目*|  
|[編譯器錯誤 C2285](compiler-error-c2285.md)|成員表示的指標已經決定 - 忽略 Pragma|  
|[編譯器錯誤 C2286](compiler-error-c2286.md)|成員的指標 '*識別碼*' 表示已設定為 *繼承*-忽略宣告|  
|[編譯器錯誤 C2287](compiler-error-c2287.md)|'*識別碼*': 繼承表示:'*inheritiance*'是 %$ m 的必要'*繼承*'|  
|編譯器錯誤 C2288|已過時。|  
|[編譯器錯誤 C2289](compiler-error-c2289.md)|相同類型的限定詞已經使用多次|  
|[編譯器錯誤 C2290](compiler-error-c2290.md)|忽略 c + + 'asm' 語法。 請使用 __asm。|  
|編譯器錯誤 C2291|無法匯出匿名命名空間。|  
|[編譯器錯誤 C2292](compiler-error-c2292.md)|'*識別碼*': 最佳情況下繼承表示︰ *inheritance1*' 宣告，但 '*和繼承 2*' 必要|  
|[編譯器錯誤 C2293](compiler-error-c2293.md)|'*識別碼*': 不合法的 __based 規範作為成員變數|  
|編譯器錯誤 C2294|無法匯出符號 '*識別碼*' 因為其具有內部連結|  
|[編譯器錯誤 C2295](compiler-error-c2295.md)|逸出 '*字元*': 在巨集定義中不合法|  
|[編譯器錯誤 C2296](compiler-error-c2296.md)|'*運算子*': 不合法，左運算元的類型為'*類型*'|  
|[編譯器錯誤 C2297](compiler-error-c2297.md)|'*運算子*': 不合法，右運算元的類型為'*類型*'|  
|[編譯器錯誤 C2298](compiler-error-c2298.md)|遺漏對界限之成員指標函式的呼叫|  
|[編譯器錯誤 C2299](compiler-error-c2299.md)|'*函式*': 行為變更︰ 明確特製化不能是複製建構函式或複製指派運算子|  
