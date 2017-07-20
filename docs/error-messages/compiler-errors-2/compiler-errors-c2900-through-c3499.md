---
title: "編譯器錯誤 C2900 透過 C2999 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2900
- C2901
- C2905
- C2907
- C2915
- C2916
- C2922
- C2924
- C2925
- C2926
- C2938
- C2949
- C2950
- C2954
- C2956
- C2960
- C2961
- C2963
- C2964
- C2965
- C2966
- C2967
- C2968
- C2972
- C2980
- C2981
- C2982
- C2983
- C2984
- C2985
- C2986
- C2987
- C2997
- C2999
helpviewer_keywords:
- C2900
- C2901
- C2905
- C2907
- C2915
- C2916
- C2922
- C2924
- C2925
- C2926
- C2938
- C2949
- C2950
- C2954
- C2956
- C2960
- C2961
- C2963
- C2964
- C2965
- C2966
- C2967
- C2968
- C2972
- C2980
- C2981
- C2982
- C2983
- C2984
- C2985
- C2986
- C2987
- C2997
- C2999
dev_langs:
- C++
ms.assetid: e3440738-e11b-4878-9ae3-6bc6c53ba461
caps.latest.revision: 16
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
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: 6ef55aa655692e6ecbd1550bb1ace2eca01bdbad
ms.contentlocale: zh-tw
ms.lasthandoff: 04/24/2017

---
# <a name="compiler-errors-c2900-through-c2999"></a>編譯器錯誤 C2900 透過 C2999
這部分文件中的文章包含 Visual C++ 編譯器錯誤的子區段的相關資訊。 您可以在此存取資訊，或是在 Visual Studio 的 [ **輸出** ] 視窗，您可以選取錯誤代碼然後選擇 F1 鍵。  
  
> [!NOTE]
>  並非每個[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]錯誤會記載於 MSDN 中。 在許多情況下，診斷訊息會提供所有可用的資訊。 如果您認為錯誤訊息需要補充說明，請告訴我們。 您可以使用這個頁面上的回函表單或移至 Visual Studio 中的功能表列並選擇**協助**，**回報 Bug**，或您可以提出建議或 bug 報告上[Microsoft Connect](http://connect.microsoft.com/VisualStudio)。  
  
 您可能會發現其他協助的 MSDN 公共論壇上錯誤及警告。 [Visual c + + 語言](http://go.microsoft.com/fwlink/?LinkId=158195)論壇是關於問題及討論[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]語言語法和編譯器。 [Visual c + + 一般](http://go.microsoft.com/fwlink/?LinkId=158194)論壇是關於問題[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]其他論壇中沒有討論之。 您也可能會在找到關於錯誤和警告的說明[堆疊溢位](http://stackoverflow.com/)。  
  
|錯誤|訊息|  
|-----------|-------------|  
|編譯器錯誤 C2900|'*宣告子*': WinRT 類別中的成員函式樣板必須是 'private'、 'internal' protected private'|  
|編譯器錯誤 C2901|'*識別碼*': 泛型介面或委派不能是公用|  
|[編譯器錯誤 C2902](compiler-error-c2902.md)|'*語彙基元*': 未預期語彙基元下列' 範本/泛型 '，必須是識別項|  
|[編譯器錯誤 C2903](compiler-error-c2903.md)|'*識別碼*': 符號不是類別範本/泛型或函式範本/泛型|  
|[編譯器錯誤 C2904](compiler-error-c2904.md)|'*識別碼*': 已經使用目前範圍中的範本名稱|  
|編譯器錯誤 C2905|已過時。|  
|[編譯器錯誤 C2906](compiler-error-c2906.md)|'*範本*': 明確特製化必須有 '範本 <>'|  
|編譯器錯誤 C2907|暫存器引數 '*數目*' 未指定有效的暫存器號碼|  
|[編譯器錯誤 C2908](compiler-error-c2908.md)|明確特製化;'*範本*' 已經產生|  
|[編譯器錯誤 C2909](compiler-error-c2909.md)|'*識別碼*': 函式樣板的明確具現化必須有傳回類型|  
|[編譯器錯誤 C2910](compiler-error-c2910.md)|'*函式*': 無法明確特製化|  
|[編譯器錯誤 C2911](compiler-error-c2911.md)|'*成員*': 無法宣告或定義於目前的範圍內|  
|[編譯器錯誤 C2912](compiler-error-c2912.md)|明確特製化 '*宣告*' 不是函式樣板的特製化|  
|[編譯器錯誤 C2913](compiler-error-c2913.md)|明確特製化;'*宣告*' 不是類別樣板的特製化|  
|[編譯器錯誤 C2914](compiler-error-c2914.md)|'*識別碼*': 無法推算範本/泛型引數，因為函式引數是模稜兩可|  
|編譯器錯誤 C2915|'*識別碼*':'*類型*' 無法直接用在 WinRT 類型的已發行介面上。 使用 ' platform:: object ^' 改為傳遞這種類型|  
|編譯器錯誤 C2916|'*識別碼*': [FlagsAttribute] 必須 （僅限） 指定的公用列舉上使用 'unsigned int' 基礎類型|  
|[編譯器錯誤 C2917](compiler-error-c2917.md)|'*識別碼*': 無效的樣板參數|  
|[編譯器錯誤 C2918](compiler-error-c2918.md)|'*識別碼*': 索引的屬性不能用在 WinRT 類型的已發行介面上|  
|[編譯器錯誤 C2919](compiler-error-c2919.md)|'*類型*': 運算子不能用在 WinRT 類型的已發行介面上|  
|[編譯器錯誤 C2920](compiler-error-c2920.md)|重複定義: '*類型*': 類別範本/泛型已宣告為*宣告*'|  
|[編譯器錯誤 C2921](compiler-error-c2921.md)|重複定義: '*類型*': 類別範本/泛型正重新宣告為*宣告*'|  
|編譯器錯誤 C2922|'*介面*': WinRT 介面不能包含靜態成員|  
|[編譯器錯誤 C2923](compiler-error-c2923.md)|'*類型*':'*識別碼*'不是有效的範本/泛型型別引數的參數'*參數*'|  
|編譯器錯誤 C2924|__declspec(interrupt) 常式引數不在 R2 中|  
|編譯器錯誤 C2925|__declspec(interrupt) 常式不可使用浮點|  
|編譯器錯誤 C2926|'*識別碼*': 等位內匿名結構的成員不允許的預設成員初始設定式|  
|[編譯器錯誤 C2927](compiler-error-c2927.md)|'*識別碼*': 呼叫函式樣板必須有至少一個引數|  
|[編譯器錯誤 C2928](compiler-error-c2928.md)|明確具現化;'*識別碼*'不是函式或樣板類別的靜態資料成員'*類別*'|  
|[編譯器錯誤 C2929](compiler-error-c2929.md)|'*宣告子*': 明確具現化，則無法明確強制或隱藏具現化的樣板類別成員|  
|[編譯器錯誤 C2930](compiler-error-c2930.md)|'*類別*': 樣板識別碼/泛型識別重新定義的列舉值為' enum*識別碼*'|  
|[編譯器錯誤 C2931](compiler-error-c2931.md)|'*class1*': 樣板識別碼/泛型識別重複定義為成員函式的'*class2*'|  
|[編譯器錯誤 C2932](compiler-error-c2932.md)|'*類型*': 樣板識別碼/泛型識別重複定義為資料成員'*識別碼*'|  
|[編譯器錯誤 C2933](compiler-error-c2933.md)|'*類型*': 樣板識別碼/泛型識別重新定義的 typedef 成員為'*識別碼*'|  
|[編譯器錯誤 C2934](compiler-error-c2934.md)|'*類型*': 樣板識別碼/泛型識別重複定義為巢狀'*項目*'的'*識別碼*'|  
|[編譯器錯誤 C2935](compiler-error-c2935.md)|'*類型*': 樣板識別碼/泛型識別重複定義為全域函式|  
|[編譯器錯誤 C2936](compiler-error-c2936.md)|'*類型*': 樣板識別碼/泛型識別重複定義為全域資料變數|  
|[編譯器錯誤 C2937](compiler-error-c2937.md)|'*類型*': 樣板識別碼/泛型識別重複定義為全域 typedef|  
|編譯器錯誤 C2938|'*識別碼*': 無法特製化別名範本|  
|[編譯器錯誤 C2939](compiler-error-c2939.md)|'*類型*': 樣板識別碼/泛型識別重複定義為區域資料變數|  
|[編譯器錯誤 C2940](compiler-error-c2940.md)|'*類型*': 樣板識別碼/泛型識別重複定義為區域 typedef|  
|[編譯器錯誤 C2941](compiler-error-c2941.md)|'*類型*': 樣板識別碼/泛型識別重複定義為本機'*項目*'|  
|[編譯器錯誤 C2942](compiler-error-c2942.md)|'*類型*': 樣板識別碼/泛型識別重複定義為函式的型式引數|  
|[編譯器錯誤 C2943](compiler-error-c2943.md)|'*類型*': 樣板識別碼/泛型識別重複定義為樣板的型別引數|  
|[編譯器錯誤 C2944](compiler-error-c2944.md)|'*類型*': 樣板識別碼/泛型識別重複定義為樣板的數值引數|  
|[編譯器錯誤 C2945](compiler-error-c2945.md)|明確具現化 (Explicit Instantiation) 沒有參考至樣板類別 (Template-Class) 特製化|  
|[編譯器錯誤 C2946](compiler-error-c2946.md)|明確具現化;'*類型*' 不是樣板類別特製化|  
|[編譯器錯誤 C2947](compiler-error-c2947.md)|必須是 '>' 結束樣板引數，找到'*語彙基元*'|  
|[編譯器錯誤 C2948](compiler-error-c2948.md)|明確具現化;儲存類別規範 '*規範*' 特製化上不允許|  
|編譯器錯誤 C2949|/kernel 不支援使用 thread_local|  
|編譯器錯誤 C2950|已過時。|  
|[編譯器錯誤 C2951](compiler-error-c2951.md)|只允許在全域命名空間，或類別範圍使用範本/泛型宣告|  
|[編譯器錯誤 C2952](compiler-error-c2952.md)|'*宣告*': 遺漏範本/泛型參數清單的範本/泛型宣告|  
|[編譯器錯誤 C2953](compiler-error-c2953.md)|'*類型*': 類別樣板已經定義|  
|編譯器錯誤 C2954|指令文字引數不在範圍中|  
|[編譯器錯誤 C2955](compiler-error-c2955.md)|'*類型*': 使用類別範本/泛型需要範本/泛型引數清單|  
|編譯器錯誤 C2956|可調整大小解除配置函式 'operator delete （void *，size_t）' 會被選為位置解除配置函式。|  
|[編譯器錯誤 C2957](compiler-error-c2957.md)|'*語彙基元*': 左分隔符號無效︰ 必須是' <'|  
|[編譯器錯誤 C2958](compiler-error-c2958.md)|左邊*分隔符號*位於 '*檔案*(*line_number*)' 沒有正確對應|  
|[編譯器錯誤 C2959](compiler-error-c2959.md)|泛型類別或函式不可為樣板的成員|  
|編譯器錯誤 C2960|已過時。|  
|編譯器錯誤 C2961|'*函式*': 不一致的明確具現化，先前的明確具現化未指定'*引數*'|  
|[編譯器錯誤 C2962](compiler-error-c2962.md)|語法錯誤: '*語彙基元*': 樣板類別成員函式定義的結尾必須是 '}'|  
|編譯器錯誤 C2963|已過時。|  
|編譯器錯誤 C2964|已過時。|  
|編譯器錯誤 C2965|__declspec (*規範*) 不支援 /kernel|  
|編譯器錯誤 C2966|'*identifier1*': 必須為其基底類別相同的 __declspec(code_seg(...))*identifier2*'|  
|編譯器錯誤 C2967|'*識別碼*': 覆寫虛擬函式必須具有相同的 __declspec(code_seg(...)) 當做覆寫虛擬函式|  
|編譯器錯誤 C2968|'*識別碼*': 遞迴的別名宣告|  
|[編譯器錯誤 C2969](compiler-error-c2969.md)|語法錯誤: '*語彙基元*': 必須是成員函式定義為以 '}'|  
|[編譯器錯誤 C2970](compiler-error-c2970.md)|'*類型*': 樣板參數'*參數*': '*引數*': 運算式包含具有內部連結的物件不能當做非類型引數|  
|[編譯器錯誤 C2971](compiler-error-c2971.md)|'*類型*': 樣板參數'*參數*': '*引數*': 非靜態儲存期的變數不能當做非類型引數|  
|編譯器錯誤 C2972|'*類型*': 樣板參數'*參數*': 型別引數類型無效|  
|[編譯器錯誤 C2973](compiler-error-c2973.md)|'*範本*': 無效的樣板引數'*數目*'|  
|[編譯器錯誤 C2974](compiler-error-c2974.md)|'*類型*': 無效的範本/泛型引數'*參數*'，預期的類型|  
|[編譯器錯誤 C2975](compiler-error-c2975.md)|'*類型*': 無效的樣板引數'*參數*'，必須是編譯時期常數運算式|  
|[編譯器錯誤 C2976](compiler-error-c2976.md)|'*類型*': 範本/泛型引數太少|  
|[編譯器錯誤 C2977](compiler-error-c2977.md)|'*類型*': 範本/泛型引數太多|  
|[編譯器錯誤 C2978](compiler-error-c2978.md)|語法錯誤︰ 必須是 '*keyword1*'*keyword2*'; 找到的型別'*類型*' 非類型; 泛型中不支援參數|  
|[編譯器錯誤 C2979](compiler-error-c2979.md)|不支援在泛型中進行明確特製化|  
|編譯器錯誤 C2980|C++ 例外狀況處理不支援 /kernel|  
|編譯器錯誤 C2981|動態表單 '*關鍵字*' 不支援 /kernel|  
|編譯器錯誤 C2982|'*宣告*': 使用不同 __declspec(code_seg(...))︰ 已'*identifier1*「 現在 」*identifier2*'|  
|編譯器錯誤 C2983|'*宣告*': 所有宣告必須都有相同的 __declspec(code_seg(...))|  
|編譯器錯誤 C2984|已過時。|  
|編譯器錯誤 C2985|'*引數*': __declspec(code_seg(...)) 引數必須是文字區段|  
|編譯器錯誤 C2986|'*識別碼*': __declspec(code_seg(...)) 只能套用至類別或函式|  
|編譯器錯誤 C2987|宣告不能有 __declspec (code_seg ('*識別碼*')) 和 __declspec (code_seg ('*值*'))|  
|[編譯器錯誤 C2988](compiler-error-c2988.md)|無法辨認的樣板宣告/定義|  
|[編譯器錯誤 C2989](compiler-error-c2989.md)|'*類別*': 類別範本/泛型已宣告為非類別範本/泛型|  
|[編譯器錯誤 C2990](compiler-error-c2990.md)|'*類別*': 非類別範本/泛型已宣告為類別範本/泛型|  
|[編譯器錯誤 C2991](compiler-error-c2991.md)|重複定義範本/泛型參數 '*參數*'|  
|[編譯器錯誤 C2992](compiler-error-c2992.md)|'*類別*': 無效或遺漏範本/泛型參數清單|  
|[編譯器錯誤 C2993](compiler-error-c2993.md)|'*類型*': 非類型樣板參數的類型不合法'*識別碼*'|  
|[編譯器錯誤 C2994](compiler-error-c2994.md)|在樣板參數清單中未命名的類別|  
|[編譯器錯誤 C2995](compiler-error-c2995.md)|'*宣告*': 函式樣板已經定義|  
|[編譯器錯誤 C2996](compiler-error-c2996.md)|'*函式*': 遞迴函式樣板定義|  
|編譯器錯誤 C2997|'*函式*': 無法從預設成員初始設定式推算陣列界限|  
|[編譯器錯誤 C2998](compiler-error-c2998.md)|'*宣告子*': 不可為樣板定義|  
|編譯器錯誤 C2999|未知錯誤，請選擇 Visual c + + 說明 功能表上的技術支援 命令或開啟技術支援說明檔，如需詳細資訊|  
