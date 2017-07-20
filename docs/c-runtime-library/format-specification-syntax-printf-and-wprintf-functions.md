---
title: "格式規格語法：printf 和 wprintf 函式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr90.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- wprintf
dev_langs:
- C++
helpviewer_keywords:
- format specification fields for printf function
- print flag directives
- printf function, precision
- type fields, printf function
- precision fields
- printf function, format specification fields
- flag directives printf function
- type fields
ms.assetid: 664b1717-2760-4c61-bd9c-22eee618d825
caps.latest.revision: 15
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: c57231375c662134fb1f9bd0252fd3b70f051ba2
ms.lasthandoff: 04/01/2017

---
# <a name="format-specification-syntax-printf-and-wprintf-functions"></a>格式規格語法：printf 和 wprintf 函式
各種 `printf` 函式會採用格式字串和選擇性引數，然後產生格式化輸出字元序列。 格式字串包含零或多個「指示詞」，這是輸出的常值字元或是編碼的「轉換規格」，其會說明如何將輸出的引數格式化。 本主題描述格式字串中用來為轉換規格進行編碼的語法。 如需這些函式的清單，請參閱[資料流 I/O](../c-runtime-library/stream-i-o.md)。  
  
轉換規格包含選擇性及必要欄位，形式如下︰  
  
**%**[[*flags*](#flags)][[*width*](#width)][.[*precision*](#precision)][[*size*](#size)][*type*](#type)  
  
每個轉換規格的欄位都是字元，或是表示特定格式選項或轉換規範的數字。 必要的 *type* 欄位會指定要套用至引數的轉換種類。 選擇性 *flags*、*width* 及 *precision* 欄位控制其他格式的層面，例如前置空格或零、對齊方式，以及顯示的精確度。 *size* 欄位指定取用和轉換之引數的大小。  
  
基本的轉換規格只包含百分比符號和一個 *type* 字元。 例如，`%s` 指定字串轉換。 若要列印百分比符號字元，請使用 `%%`。 如果百分比符號後接著的字元不代表任何格式欄位，則會叫用無效參數處理常式。 如需詳細資訊，請參閱[參數驗證](../c-runtime-library/parameter-validation.md)。  
  
> [!IMPORTANT]
>  為了確保安全性和穩定性，請確定轉換規格字串不是使用者所定義。 例如，考慮一個請使用者輸入名稱的程式，且該程式將輸入儲存在名為 `user_name` 的字串變數。 若要印出 `user_name`，請勿採用此做法：  
>   
>  `printf( user_name ); /* Danger!  If user_name contains "%s", program will crash */`  
>   
>  相反地，請這樣做：  
>   
>  `printf( "%s", user_name );`  
  
## <a name="type"></a> 類型轉換規範
*type* 轉換規範字元指定要將對應的引數解譯成字元、字串、指標、整數還是浮點數。 *type* 字元是唯一必要的轉換規格欄位，且會在任何選擇性的欄位之後出現。  
  
遵循格式字串的引數會根據對應的 *type* 字元和選擇性的 [size](#size) 前置詞解譯。 字元類型 `char` 和 `wchar_t` 的轉換可使用 **c** 或 **C** 來指定，而單一位元組、多位元組或寬字元字串可使用 **s** 或 **S** 來指定，視使用何種格式化函式而定。 使用 **c** 和 **s** 所指定的字元和字串引數會由 `printf` 系列函式解譯為 `char` 和 `char*`，或是由 `wprintf` 系列函式解譯為 `wchar_t` 和 `wchar_t*`。 使用 **C** 和 **S** 所指定的字元和字串引數會由 `printf` 系列函式解譯為 `wchar_t` 和 `wchar_t*`，或是由 `wprintf` 系列函式解譯為 `char` 和 `char*`。 這是 Microsoft 專有的行為。  
  
像是 `short`、`int`、`long`、`long long` 的整數類型和其 `unsigned` 的變化可藉由使用 **d**、**i**、**o**、**u**、**x** 和 **X** 指定。像是 `float`、`double` 和 `long double` 的浮點類型可藉由使用 **a**、**A**、**e**、**E**、**f**、**F**、**g** 和 **G** 指定。根據預設，除非 *size* 前置詞修改它們，否則會將整數引數強制轉成 `int` 類型，且會將浮點引數強制轉成 `double`。 在 64 位元系統上，`int` 是 32 位元值；因此，除非使用 **ll** 或 **I64** 的 *size* 前置詞，否則 64 位元整數在為了輸出而格式化時會遭到截斷。 由 **p** 指定的指標類型會使用此平台的預設指標。  
  
> [!NOTE]
>  **Z** 類型字元以及搭配 `printf` 和 `wprintf` 函式使用時的 **c**、**C**、**s** 及 **S** 類型字元的行為，是 Microsoft 延伸模組。 ISO C 標準在所有格式設定函式中，一致地對窄字元和字串使用 **c** 和 **s**，並對寬字元和字串使用 **C** 和 **S**。   
  
### <a name="type-field-characters"></a>類型欄位字元  
  
|類型字元|引數|輸出格式|  
|--------------------|--------------|-------------------|  
|**c**|字元|搭配 `printf` 函式使用時，會指定單一位元組字元；搭配 `wprintf` 函式使用時，會指定寬字元。|  
|**C**|字元|搭配 `printf` 函式使用時，會指定寬字元；搭配 `wprintf` 函式使用時，會指定單一位元組字元。|  
|**d**|整數|帶正負號的十進位整數。|  
|**i**|整數|帶正負號的十進位整數。|  
|**o**|整數|不帶正負號的八進位整數。|  
|**u**|整數|不帶正負號的十進位整數。|  
|**x**|整數|不帶正負號的十六進位整數；使用 "abcdef"。|  
|**X**|整數|不帶正負號的十六進位整數；使用 "ABCDEF"。|  
|**e**|浮點|具有 [-]*d.dddd*__e±__*dd*[*d*] 形式之帶有正負號的值，其中 *d* 是一個十進位數字，*dddd* 是一或多個十進位數字，*dd*[*d*] 是兩個或三個十進位數字 (取決於[輸出格式](../c-runtime-library/set-output-format.md)和該指數的大小)。|  
|**E**|浮點|與 **e** 格式相同，除了由 **E** 而非 **e** 引入該指數以外。|  
|**f**|浮點|具有 [-]*dddd*__.__*dddd* 形式之帶正負號的值，其中 *dddd* 是一或多個十進位數字。 小數點前面的位數取決於數字的大小，小數點後面的位數則取決於要求的精確度，或是預設為六。|  
|**F**|浮點|與 **f** 格式相同，除了無限及 NAN 輸出為大寫以外。|  
|**g**|浮點|帶正負號的值會以 **f** 或 **e** 格式顯示，視何種格式對所指定的值和精確度而言較為精簡。 只有在該值的指數小於 -4 或大於等於 *precision* 引數時會使用 **e** 格式。 會截斷尾端的零，僅當一或多個數字位於小數點後面時，才會顯示小數點。|  
|**G**|浮點|與 **g** 格式相同，除了由 **E** 而非 **e** 在適當時引入該指數以外。|  
|**a**|浮點|具有 [-]0x*h.hhhh*__p±__*dd* 形式之帶正負號的十六進位雙精確度浮點數的值，其中 *h.hhhh* 是尾數的十六進位數 (使用小寫字母)，而 *dd* 是指數的一或多個位數。 指定小數點之後位數的精確度。|  
|**A**|浮點|具有 [-]0X*h.hhhh*__P±__*dd* 形式之帶正負號的十六進位雙精確度浮點數的值，其中 *h.hhhh* 是尾數的十六進位數 (使用大寫字母)，而 *dd* 是指數的一或多個位數。 指定小數點之後位數的精確度。|  
|**n**|整數的指標|目前已成功寫入此資料流或緩衝區的字元數。 會將這個值儲存在整數中，該整數的位址會做為引數而受指定。 引數大小規格前置詞可以控制指向整數的大小。 **n** 規範預設會停用；如需資訊，請參閱重要安全性注意事項。|  
|**p**|指標類型|顯示引數為十六進位數字的位址。|  
|**s**|字串|當搭配 `printf` 函式使用時，會指定單一位元組或多位元組字元字串；當搭配 `wprintf` 函式使用時，會指定寬字元字串。 字元會顯示，直到第一個 null 字元或達到 *precision* 值為止。|  
|**S**|字串|當搭配 `printf` 函式使用時，會指定寬字元字串；當搭配 `wprintf` 函式使用時，會指定單一位元組或多位元組字元字串。 字元會顯示，直到第一個 null 字元或達到 *precision* 值為止。|  
|**Z**|`ANSI_STRING` 或 `UNICODE_STRING` 結構|當 [ANSI_STRING](http://msdn.microsoft.com/library/windows/hardware/ff540605.aspx) 或 [UNICODE_STRING](http://msdn.microsoft.com/library/windows/hardware/ff564879.aspx) 結構的位址作為引數傳遞時，顯示結構的 `Buffer` 欄位所指向之緩衝區中所包含的字串。 使用 **w** 的 *size* 修飾詞前置來指定 `UNICODE_STRING` 引數，例如 `%wZ`。 該結構的 `Length` 欄位必須設定為此字串的長度，以位元組為單位。 該結構的 `MaximumLength` 欄位必須設定為此緩衝區的長度，以位元組為單位。<br /><br /> 通常，**Z** 類型字元只在驅動程式偵錯函式中使用，該函式使用像是 `dbgPrint` 和 `kdPrint` 的轉換規格。|  
  
自 Visual Studio 2015 起，如果對應於浮點轉換規範 (**a**、**A**、**e**、**E**、**f**、**F**、**g**、**G**) 的引數是無限大、不確定或 NAN，則格式化輸出符合 C99 標準。 下表列出格式化輸出︰  
  
|值|輸出|  
|-----------|------------|  
|infinity|`inf`|  
|無訊息 NaN|`nan`|  
|發出 NAN 訊號|`nan(snan)`|  
|不確定的 NAN|`nan(ind)`|  
  
其中任何一個值都可以有正負號的前置詞。 如果浮點 *type* 轉換規範字元是大寫字母，則輸出的格式也是以大寫字母呈現。 例如，如果格式規範是 `%F` 而不是 `%f`，則無限值會格式化為 `INF` 而不是 `inf`。 `scanf` 函式也可剖析這些字串，因此這些值可以往返 `printf` 和 `scanf` 函式。
  
在 Visual Studio 2015 之前，CRT 對無限大、不確定及 NAN 值的輸出使用不同的非標準格式︰  
  
|值|輸出|  
|-----------|------------|  
|+ 無限大|`1.#INF`*隨機數字*|  
|- infinity|`-1.#INF`*隨機數字*|  
|不確定 (與無訊息的 NaN 相同)|*數字* `.#IND` *隨機數字*|  
|NaN|*數字* `.#NAN` *隨機數字*|  
  
其中任何一項都可能有正負號的前置詞，也可能根據欄位寬度和精確度而有稍微不同的格式 (有時會有不尋常的效果)。 例如，`printf("%.2f\n", INFINITY)` 可能會列印 `1.#J`，因為有可能會將 #INF 「四捨五入」為 2 位數的精確度)。

> [!NOTE]
>  如果對應到 `%s`或 `%S` 的引數或是對應到 `%Z` 的引數之 `Buffer` 欄位為 null 指標，則會顯示 "(null)"。  
  
> [!NOTE]
>  在所有指數格式中，要顯示之指數的最小位數為二，僅在必要時使用三個位數。 透過 [_set_output_format](../c-runtime-library/set-output-format.md) 函式，您可使用為 Visual Studio 2013 及之前版本撰寫的程式碼，將回溯相容性的所顯示位數設為三。  
  
> [!IMPORTANT]
>  因為 `%n` 格式本來就不安全，所以根據預設會予以停用。 如果 `%n` 是在格式字串中遇到，則會叫用無效參數處理常式，如[參數驗證](../c-runtime-library/parameter-validation.md)中所述。 若要啟用 `%n` 支援，請參閱 [_set_printf_count_output](../c-runtime-library/reference/set-printf-count-output.md)。  
  
## <a name="flags"></a>旗標指示詞
轉換規格的第一個選擇性欄位包含*旗標指示詞*，該指示詞為零或多個旗標字元，其指定輸出對齊並控制符號、空白字元、前置字元為零、小數位數，以及八進位和十六進位前置詞的輸出。 轉換規格中可能會出現多個旗標指示詞，而旗標字元可按照任何順序出現。  
  
### <a name="flag-characters"></a>旗標字元  
  
|旗標|意義|預設|  
|----------|-------------|-------------|  
|**-**|靠左對齊給定欄位寬度內的結果。|靠右對齊。|  
|**+**|如果輸出值是帶正負號的類型，則使用正負號 (+ 或 -) 作為其前置詞。|僅為帶負號 (-) 的值顯示符號。|  
|**0**|如果 *width* 前面加上 **0**，則會新增前置字元為零，直到達到最小寬度為止。 如果 **0** 和 **-** 同時出現，則會略過 **0**。 如果整數格式 (**i****u****x**、**X**、**o**、**d**) 指定為 **0**，且精確度規格也同時出現 (例如，`%04.d`) 則會略過 **0**。 如果為 **a** 或 **A** 浮點格式指定 **0**，則尾數前面會加上前置字元為零 (在 `0x` 或 `0X` 前置詞之後)。|無填補。|  
|**blank** (' ')|如果輸出值帶有正負號且為正值，則在該輸出值前面加上空白字元。 如果空白字元及 + 旗標同時出現，則會略過空白字元。|不會出現空白字元。|  
|**#**|與 **o****x** 或 **X** 格式搭配使用時，**#** 旗標分別會使用 0、0 x 或 0X，作為任何非零輸出值的前置詞。|不會出現空白字元。|  
||與 **e**、**E**、**f**、**F**、**a** 或 **A** 格式搭配使用時，**#** 旗標會強制輸出值包含小數點。|小數點只有在後面有數字時才會顯示。|  
||與 **g** 或 **G** 格式搭配使用時，**#** 旗標會強制輸出值包含小數點，並避免截斷行尾零。<br /><br /> 與 **c**、**d**、**i**、**u**或 **s** 搭配使用時會予以略過。|小數點只有在後面有數字時才會顯示。 行尾零會被截斷。|  
  
## <a name="width"></a> 寬度規格
在轉換規格中，選擇性寬度規格欄位會在任何 *flags* 字元後面出現。 *width* 引數是非負數十進位整數，其控制輸出的字元數目下限。 如果輸出值中的字元數小於指定的寬度，空白字元會新增至值的左邊或右邊，取決於是否已指定靠左對齊的旗標 (**-**)，直到達到最小寬度為止。 如果 *width* 前面加上 0，前置字元為零會新增至整數或浮點數轉換，直到到達最小寬度為止 (轉換為無限或 NAN 則除外)。  
  
 寬度規格一律不會截斷值。 輸出值中的字元數目若大於指定的寬度，或如果未給定 *width*，則值的所有字元皆為輸出，視「精確度」規格而定。  
  
 如果寬度規格是星號 (`*`)，來自引數清單的 `int` 引數就會提供值。 *width* 引數的前面必須加上已在引數清單中格式化的值，如下例所示︰  
  
 `printf("%0*f", 5, 3);  /* 00003 is output */`  
  
 轉換規格中遺漏或小型的 *width* 值不會造成截斷輸出值。 如果轉換的結果寬度大於 *width* 值，欄位會展開以包含轉換結果。  
  
## <a name="precision"></a> 精確度規格
在轉換規格中，第三個選擇性欄位是精確度規格。 它包含句號 (.)、後面接著非負值的十進位整數，視轉換類型而定，它指定字串字元數目、小數位數或要輸出的有效位數。  
  
 不同於寬度規格，精確度規格會造成輸出值截斷或浮點數值四捨五入。 如果 *precision* 指定為 0，而要轉換的值為 0，則結果為無字元輸出，如下例所示︰  
  
 `printf( "%.0d", 0 );      /* No characters output */`  
  
 如果精確度規格是星號 (\*)，來自引數清單的 `int` 引數就會提供值。 在引數清單中， *precision* 引數的前面必須加上已格式化的值，如下例所示︰  
  
 `printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`  
  
 省略 *precision* 時，*type* 字元會決定解譯 *precision* 或預設的精確度，如下表所示。  
  
### <a name="how-precision-values-affect-type"></a>精確度值如何影響類型  
  
|類型|意義|預設|  
|----------|-------------|-------------|  
|**a**、**A**|指定小數點之後位數的精確度。|預設精確度為 13。 如果精確度為 0，除非使用 **#** 旗標，否則不會列印小數點。|  
|**c**、**C**|精確度無效果。|列印字元。|  
|**d**、**i**、**o**、**u**、**x**、**X**|精確度指定要列印的最小位數。 如果引數中的位數小於 *precision*，輸出值左邊以零填補。 當位數超過 *precision* 就不會截斷值。|預設精確度為 1。|  
|**e****E**|精確度指定小數點後要列印的位數。 最後一個列印數字已四捨五入。|預設精確度為 6。 如果 *precision* 是 0，或句點 (.) 後面沒有數字，則不列印小數點。|  
|**f**、**F**|精確度值指定小數點後的位數。 如果出現小數點，它的前面至少要出現一個數字。 值會四捨五入到適當的位數。|預設精確度為 6。 如果 *precision* 是 0，或句點 (.) 後面沒有數字，則不列印小數點。|  
|**g**、**G**|精確度指定列印的最大有效位數。|列印六個有效位數，並截斷任何結尾的零。|  
|**s**、**S**|精確度指定要列印的最大字元數。 不列印超過 *precision* 的字元。|字元一直列印到遇到 Null 字元。|  
  
## <a name="size"></a>引數大小規格
在轉換規格中，*size*欄位是 *type* 轉換規範的引數長度修飾詞。 *type* 欄位的 *size* 欄位前置詞 (**hh**、**h**、**j**、**l** (lowercase L)、**L**、**ll**、**t**、**w**、**z**、**I** (大寫 i)、**I32** 及 **I64**) 會根據所修改的轉換規範來指定對應引數的「大小」：長或短、32 位元或 64 位元、單一位元組字元或寬字元。 這些大小前置詞可在 `printf` 和 `wprintf` 系列函式中搭配 *type* 字元使用，以指定引數大小的轉譯，如下表所示。 *size* 對於某些引數類型是選擇性欄位。 未指定大小前置詞時，格式子會使用整數引數 (例如帶正負號或不帶正負號的 `char`、`short`、`int`、`long` 和列舉類型) 作為 32 位元 `int` 類型，並使用 `float`、`double` 及 `long double` 浮點引數作為 64 位元 `double` 類型。 這符合變數引數清單的預設引數提升規則。 如需引數提升的詳細資訊，請參閱[後置運算式](../cpp/postfix-expressions.md)中的＜省略符號和預設引數＞。 在 32 位元和 64 位元系統上，64 位元整數引數的轉換規格必須包含大小前置詞 **ll** 或 **I64**。 否則，格式子的行為未定義。  
  
某些類型在 32 位元和 64 位元程式碼中的大小不同。 例如，`size_t` 在針對 x86 所編譯的程式碼中的長度為 32 位元，在針對 x64 所編譯的程式碼中的長度為 64 位元。 若要針對變動寬度類型建立無從驗證平台的格式化程式碼，您可以使用變動寬度的引數大小修飾詞。 您也可以使用 64 位元引數大小修飾詞，並明確地將變動寬度的引數類型升階至 64 位元。 Microsoft 專有的 **I** (大寫 i) 引數大小修飾詞會處理變動寬度的整數引數，但建議您使用類型特定的 **j**、**t** 及 **z** 修飾詞供可攜性用。  
  
### <a name="size-prefixes-for-printf-and-wprintf-format-type-specifiers"></a>printf 和 wprintf 格式類型規範的大小前置詞  
  
|若要指定|使用前置詞|類型規範為|  
|----------------|----------------|-------------------------|  
|`char`<br />`unsigned char`|**hh**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`short int`<br />`short unsigned int`|**h**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`__int32`<br />`unsigned __int32`|**I32**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`__int64`<br />`unsigned __int64`|**I64**|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`intmax_t`<br />`uintmax_t`|**j** 或 **I** (大寫 i)|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`long double`|**l** (小寫 L) 或 **L**|**a**、**A**、**e**、**E**、**f**、**F**、**g** 或 **G**|  
|`long int`<br />`long unsigned int`|**l** (小寫 L)|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`long long int`<br />`unsigned long long int`|**ll** (小寫 LL)|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`ptrdiff_t`|**t** 或 **I** (大寫 i)|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|`size_t`|**z** 或 **I** (大寫 i)|**d**、**i**、**o**、**u**、**x** 或 **X**|  
|單一位元組字元|**h**|**c** 或 **C**|  
|寬字元|**l** (小寫 L) 或 **w**|**c** 或 **C**|  
|單一位元組字元字串|**h**|**s**、**S** 或 **Z**|  
|寬字元字串|**l** (小寫 L) 或 **w**|**s**、**S** 或 **Z**|  
  
`intmax_t`、`uintmax_t`、`ptrdiff_t` 及 `size_t` 類型在 32 位元平台上為 `__int32` 或 `unsigned __int32`，而在 64 位元平台上為 `__int64` 或 `unsigned __int64`。 **I** (大寫 i)、**j**、**t** 及 **z** 大小前置詞為平台採用正確的引數寬度。  
  
在 Visual C++ 中，雖然 `long double`類型不同，但具有相同的內部表示法 `double`。  
  
**hc** 或 **hC** 類型規範，與 `printf` 函式中的 **c** 和 `wprintf` 函式中的 **C** 同義)。 **lc**、**lC**、**wc** 或 **wC** 類型規範，與 `printf` 函式中的 **C** 和 `wprintf` 函式中的 **c** 同義)。 **hs** 或 **hS** 類型規範，與 `printf` 函式中的 **s** 和 `wprintf` 函式中的 **S** 同義)。 **ls**、**lS**、**ws** 或 **wS** 類型規範，與 `printf` 函式中的 **S** 和 `wprintf` 函式中的 **s** 同義)。  
  
> [!NOTE]
>  **I** (大寫 i)、**I32**、**I64** 及 **w** 引數大小修飾詞前置詞為 Microsoft 延伸模組，且與 ISO C 不相容。 **h** 前置詞與類型 `char` 的資料搭配使用時，以及 **l** 前置詞與類型 `double` 的資料搭配使用時，這些前置詞都是 Microsoft 延伸模組。  
  

## <a name="see-also"></a>另請參閱  
 [printf、_printf_l、wprintf、_wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s、_printf_s_l、wprintf_s、_wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [printf_p 位置參數](../c-runtime-library/printf-p-positional-parameters.md)   
