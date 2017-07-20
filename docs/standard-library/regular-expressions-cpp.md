---
title: "規則運算式 (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Visual C++, regular expressions
- regular expressions, Visual C++
- regular expressions
ms.assetid: aafe202a-1d96-4b36-a270-d676dfd3c51c
caps.latest.revision: 12
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
ms.openlocfilehash: ac4dc70360682aff3a28eabeed0e4f05e4c509a8
ms.contentlocale: zh-tw
ms.lasthandoff: 04/24/2017

---
# <a name="regular-expressions-c"></a>規則運算式 (C++)
C + + 標準程式庫支援多個規則運算式文法中。 本主題討論可用的文法變化時使用規則運算式。  
  
##  <a name="regexgrammar"></a> 規則運算式文法  
若要使用規則運算式文法所指定使用其中一種`std::regex_constants::syntax_option_type`列舉值。 這些規則運算式文法定義 std::regex_constants:

-   `ECMAScript`︰ 這是最接近的 JavaScript 和.NET 語言所使用的文法。
-   `basic`: POSIX 基本規則運算式或 BRE。
-   `extended`︰ 規則運算式或 ERE 的擴充 POSIX。
-   `awk`︰ 這是`extended`，但它還有其他非列印字元的逸出。
-   `grep`︰ 這是`basic`，但它也可讓新行字元 ('\n') 字元來分隔替代。
-   `egrep`︰ 這是`extended`，但它也可讓新行字元來分隔 alternatios。

根據預設，如果已指定沒有文法，`ECMAScript`假設。 您可以指定只有一個文法。  
  
除了文法中，您可以套用數個旗標︰  
-   `icase`︰ 比對時忽略大小寫。  
-   `nosubs`︰ 忽略標示的相符項目 （也就是運算式括號括住）。會不儲存任何替代項目。  
-   `optimize`︰ 請比對速度更快，在可能大於建構時的費用。  
-   `collate`︰ 使用區分地區設定的定序順序 （例如，"[a 到 z]"格式的範圍）。  
  
零或多個旗標可能會結合指定的規則運算式引擎行為的文法。 如果只指定旗標，`ECMAScript`會假定為文法。

### <a name="element"></a>項目  
 項目可以是下列其中一項：  
  
-   「一般字元」，符合目標序列中的相同字元。  
  
-   「萬用字元」'.'，符合目標序列中新行字元以外的任何字元。  
  
-   格式為 "[`expr`]" 的「括號運算式」，其符合目標序列中且在運算式 `expr` 所定義集合中的字元或定序項目，或者，若格式為 "[^`expr`]"，則符合目標序列中但不在運算式 `expr` 所定義集合中的字元或定序項目。  
  
     `expr` 運算式可能包含下列項目的任何組合：  
  
    -   個別字元。 會將該字元加入到 `expr` 定義的這個集合。  
  
    -   格式為 "`ch1`-`ch2`" 的「字元範圍」。 會將封閉範圍 [`ch1`, `ch2`] 中的值所代表的字元加入到 `expr` 定義的這個集合。  
  
    -   格式為 "[:`name`:]" 的「字元類別」。 會將具名類別的字元加入至 `expr` 定義的這個集合。  
  
    -   格式為 "[=`elt`=]" 的「等價類別」(Equivalence Class)。 會將相當於 `elt` 的定序項目加入至 `expr` 定義的這個集合。  
  
    -   格式為 "[.`elt`.]" 的「定序符號」。 會將定序項目 `elt` 加入到 `expr` 定義的這個集合。  
  
-   「錨點」。 錨點 '^' 符合目標序列開頭，錨點 '$' 符合目標序列結尾。  
  
 在 `basic` 和 `grep` 中，格式為 "( *subexpression* )" 或 "\\( *subexpression* \\)" 的「擷取群組」，其符合目標序列中透過分隔符號之間的模式進行比對的字元序列。  
  
-   格式為 "\\`k`" 的「識別逸出」，其符合目標序列中的字元 `k`。  
  
 範例：  
  
-   "a" 符合目標序列 "a"，但不符合目標序列 "B"、"b" 或 "c"。  
  
-   "." 符合所有目標序列 "a"、"B"、"b" 和 "c"。  
  
-   "[b-z]" 符合目標序列 "b" 和 "c"，但不符合目標序列 "a" 或 "B"。  
  
-   "[:lower:]" 符合目標序列 "a"、"b" 和 "c"，但不符合目標序列 "B"。  
  
-   "(a)" 符合目標序列 "a" 並將擷取群組 1 與子序列 "a" 關聯，但不符合目標序列 "B"、"b" 或 "c"。  
  
 在 `ECMAScript`、`basic` 和 `grep`，項目也可以是格式為 "\\`dd`" 的「反向參考」，其中`dd` 表示十進位值 N，其符合目標序列中由第 N 個「擷取群組」所比對之相同字元序列的字元序列。 例如，"(a)\1" 符合目標序列 "aa"，因為第一個 (且唯一) 擷取群組符合初始序列 "a"，而 \1 符合最終序列 "a"。  
  
 在 `ECMAScript` 中，項目也可以是下列其中一項：  
  
-   格式為 "(: *subexpression* )" 的「非擷取群組」。 符合目標序列中由分隔符號之間的模式所比對的字元序列。  
  
-   格式為 "\f"、"\n"、"\r"、"\t" 或 "\v" 的有限「檔案格式逸出」。 這些分別符合目標序列中的換頁字元、新行字元、歸位字元、水平索引標籤和垂直索引標籤。  
  
-   格式為 "(= *subexpression* )" 的「正判斷提示」。 符合目標序列中由分隔符號之間的模式所比對的字元序列，但是不會變更目標序列中的相符項目位置。  
  
-   「負判斷提示」，其格式為 "(! *subexpression* )"。 符合目標序列中與分隔符號之間的模式不相符的任何字元序列，而且不會變更目標序列中的相符項目位置。  
  
-   格式為 "\x`hh`" 的「十六進位逸出序列」。 符合目標序列中由兩個十六進位數字 `hh` 表示的字元。  
  
-   格式為 "\u`hhhh`" 的「Unicode 逸出序列」。 符合目標序列中由四個十六進位數字 `hhhh` 表示的字元。  
  
-   格式為 "\c`k`" 的「控制項逸出序列」。 符合由字元 `k` 所指名的控制字元。  
  
-   格式為 "\b" 的「字邊界判斷提示」。 當目標序列的目前位置緊接在「字邊界」之後時相符。  
  
-   格式為 "\B" 的「負字邊界判斷提示」。 當目標序列的目前位置不是緊接在「字邊界」之後時相符。  
  
-   格式為 "\d"、"\D"、"\s"、"\S"、"\w"、"\W" 的「DSW 逸出字元」。 為字元類別提供簡短名稱。  
  
 範例：  
  
-   "(:a)" 符合目標序列 "a"，但 "(:a)\1" 無效，因為沒有擷取群組 1。  
  
-   "(=a)a" 符合目標序列 "a"。 正判斷提示符合目標序列中的初始序列 "a"，而在規則運算式中的最後 "a" 符合目標序列中的初始序列 "a"。  
  
-   "(!a)a" 不符合目標序列 "a"。  
  
-   "a\b." 符合目標序列 "a~"，但不符合目標序列 "ab"。  
  
-   "a\B." 符合目標序列 "ab"，但不符合目標序列 "a~"。  
  
 在 `awk` 中，項目也可以是下列其中一項：  
  
-   格式為 "\\\\"、"\a"、"\b"、"\f"、"\n"、"\r"、"\t" 或 "\v" 的「檔案格式逸出」。 這些分別符合目標序列中的反斜線、警示、退格鍵、換頁字元、新行字元、歸位字元、水平索引標籤和垂直索引標籤。  
  
-   格式為 "\\`ooo`" 的「八進位逸出序列」。 符合目標序列中由一個、兩個或三個八進位數字 `ooo` 表示的字元。  
  
### <a name="repetition"></a>重複  
 除了「正判斷提示」、「負判斷提示」或「錨點」之外的任何項目後面都可接著重複計數。 在 `basic` 和 `grep` 中，最常見的重複計數格式為 "{`min`,`max`}" 或 "\\{`min`,`max`\\}"。 後面接著這個重複計數格式的項目至少符合與項目相符之序列的 `min` 後續發生次數，但不超過 `max` 後續發生次數。 例如，"a{2,3}" 符合目標序列 "aa" 和目標序列 "aaa"，但不符合目標序列 "a" 或目標序列 "aaaa"。  
  
 重複計數也可以採用下列其中一個格式：  
  
-   `basic` 和 `grep` 中的 "{`min`}" 或 "\\{`min`\\}"。 相當於 "{`min`,`min`}"。  
  
-   `basic` 和 `grep` 中的 "{`min`,}" 或 "\\{`min`,\\}"。 相當於 "{`min`,unbounded}"。  
  
-   "*". 相當於 "{0,unbounded}"。  
  
 例如：  
  
-   "a{2}" 符合目標序列 "aa"，但不符合目標序列 "a" 或目標序列 "aaa"。  
  
-   "a{2,}" 符合目標序列 "aa"、目標序列 "aaa" 等等，但不符合目標序列 "a"。  
  
-   "a*" 符合目標序列 ""、目標序列 "a"、目標序列 "aa" 等等。  
  
 對於除了 `basic` 和 `grep` 的所有文法，重複計數也可以採用下列其中一個格式：  
  
-   ""。 相當於 "{0,1}"。  
  
-   "+". 相當於 "{1,unbounded}"。  
  
 範例：  
  
-   "a" 符合目標序列 "" 和目標序列 "a"，但不符合目標序列 "aa"。  
  
-   "a+" 符合目標序列 "a"、目標序列 "aa" 等等，但不符合目標序列 ""。  
  
 在 `ECMAScript` 中，所有重複計數格式後面都可接著字元 ''，其會指定「非窮盡重複」。  
  
### <a name="concatenation"></a>串連  
 規則運算式項目 (不論是否有「重複計數」) 可串連來形成較長的規則運算式。 結果運算式符合由個別項目所比對之序列串連而成的目標序列。 例如，"a{2,3}b" 符合目標序列 "aab" 和目標序列 "aaab"，但不符合目標序列 "ab" 或目標序列 "aaaab"。  
  
### <a name="alternation"></a>替代  
 在所有規則運算式文法 (但 `basic` 和 `grep` 除外) 中，串連的規則運算式後面可以接著字元 '&#124;' 和另一個串連的規則運算式。 任何數目的串連規則運算式可透過這種方式合併。 結果運算式符合與一個或多個串連規則運算式相符的任何目標序列。  
  
 當一個以上的串連規則運算式符合目標序列時，`ECMAScript` 會選擇符合序列的第一個串連規則運算式做為相符項 (「第一個相符」)，其他規則運算式文法則會選擇達到「最長相符」的串連規則運算式。 例如，"ab&#124;cd" 符合目標序列 "ab" 和目標序列 "cd"，但不符合目標序列 "abd" 或目標序列 "acd"。  
  
 在 `grep` 和 `egrep`，新行字元 ('\n') 可以用來分隔替代。  
  
### <a name="subexpression"></a>子運算式  
 在 `basic` 和 `grep`，子運算式是串連。 在其他規則運算式文法中，子運算式是替代。  
  
##  <a name="grammarsummary"></a> 文法摘要  
 下表摘要說明各種規則運算式文法的功能：  
  
|項目|基本|延伸|ECMAScript|grep|egrep|awk|  
|-------------|---------|---------|----------|----------|-----------|---------|  
|使用 '&#124;' 的替代||+|+||+|+|  
|使用 '\n' 的替代||||+|+||  
|錨點|+|+|+|+|+|+|  
|反向參考|+||+|+|||  
|括號運算式|+|+|+|+|+|+|  
|使用 "()" 的擷取群組||+|+||+|+|  
|使用 "\\(\\)" 的擷取群組|+|||+|||  
|控制項逸出序列|||+||||  
|DSW 逸出字元|||+||||  
|檔案格式逸出|||+|||+|  
|十六進位逸出序列|||+||||  
|識別逸出|+|+|+|+|+|+|  
|負判斷提示|||+||||  
|負字邊界判斷提示|||+||||  
|非擷取群組|||+||||  
|非窮盡重複|||+||||  
|八進位逸出序列||||||+|  
|一般字元|+|+|+|+|+|+|  
|正判斷提示|||+||||  
|使用 "{}" 的重複||+|+||+|+|  
|使用 "\\{\\}" 的重複|+|||+|||  
|使用 '*' 的重複|+|+|+|+|+|+|  
|使用 '' 和 '+' 的重複||+|+||+|+|  
|Unicode Escape Sequence - Unicode 逸出序列|||+||||  
|萬用字元|+|+|+|+|+|+|  
|Word Boundary Assert - 字邊界判斷提示|||+||||  
  
##  <a name="semanticdetails"></a> 語意詳細資料  
  
### <a name="anchor"></a>錨點  
 錨點符合目標字串中的位置，而非字元。 '^' 符合目標字串開頭，而 '$' 符合目標字串結尾。  
  
### <a name="back-reference"></a>反向參考  
 反向參考是一個反斜線，後面接著十進位值 N。它會比對第 N 個「擷取群組」的內容。 N 值不能大於反向參考之前的擷取群組數目。 在 `basic` 和 `grep`，N 值取決於反斜線後面的十進位數字。 在 `ECMAScript`，N 值取決於緊接在反斜線後面的所有十進位數字。 因此，在 `basic` 和 `grep`，N 值絕不會超過 9，即使規則運算式有九個以上的擷取群組。 在 `ECMAScript`，N 值是無限制的。  
  
 例如：  
  
-   "((a+)(b+))(c+)\3" 符合目標序列 "aabbbcbbb"。 反向參考 "\3" 符合第三個擷取群組中的文字，也就是 "(b+)"。 它不符合目標序列 "aabbbcbb"。  
  
-   "(a)\2" 無效。  
  
-   "(b(((((((((a))))))))))\10" 在 `basic` 及 `ECMAScript` 有不同的意義。 在 `basic` 中，反向參考是 "\1"。 反向參考符合第一個擷取群組 (也就是開頭為 "(b"、結尾為最終 ")" 且在反向參考之前的擷取群組)，而最終 '0' 符合一般字元 '0'。 在 `ECMAScript` 中，反向參考是 "\10"。 它符合第十個擷取群組，也就是最內部的擷取群組。  
  
### <a name="bracket-expression"></a>括號運算式  
 括號運算式會定義一組字元及「定序項目」。 當括號運算式開頭為字元 '^' 時，如果集合中沒有與目標序列中的目前字元相符的任何項目，比對成功。 否則，如果集合中有與目標序列中的目前字元相符的任何一個項目，比對成功。  
  
 字元集可以透過列出「個別字元」、「字元範圍」、「字元類別」、「等價類別」和「定序符號」的任意組合來定義。  
  
### <a name="capture-group"></a>擷取群組  
 擷取群組將其內容標記為規則運算式文法中的單一單位，而且會標記符合其內容的目標文字。 與每個擷取群組相關聯的標籤是數字，透過計算標示擷取群組的左括號，直到標示目前擷取群組的左括號所決定。 在這個實作中，擷取群組數目上限是 31。  
  
 例如：  
  
-   "ab+" 符合目標序列 "abb"，但不符合目標序列 "abab"。  
  
-   "(ab)+" 不符合目標序列 "abb"，但符合目標序列 "abab"。  
  
-   "((a+)(b+))(c+)" 符合目標序列 "aabbbc"，而且將擷取群組 1 與子序列 "aabbb" 關聯、將擷取群組 2 與子序列 "aa" 關聯、將擷取群組 3 與子序列 "bbb" 關聯，以及將擷取群組 4 與子序列 "c" 關聯。  
  
### <a name="character-class"></a>字元類別  
 括號運算式中的字元類別會將具名類別中的所有字元加入至括號運算式所定義的字元集。 若要建立字元類別，請使用 "[:"，後面接著類別名稱，後面接著 ":]"。 在內部，字元類別名稱是透過呼叫 `id = traits.lookup_classname` 所辨識。 如果 `ch` 傳回 true，字元 `traits.isctype(ch, id)` 屬於這種類別。 預設 `regex_traits` 範本支援下表中的類別名稱。  
  
|類別名稱|描述|  
|----------------|-----------------|  
|"alnum"|小寫字母、大寫字母和數字|  
|"alpha"|小寫字母和大寫字母|  
|"blank"|空格或定位鍵|  
|"cntrl"|「檔案格式逸出」字元|  
|"digit"|digits|  
|"graph"|小寫字母、大寫字母、數字和標點符號|  
|"lower"|小寫字母|  
|"print"|小寫字母、大寫字母、數字、標點符號和空格|  
|"punct"|標點符號|  
|"space"|空間|  
|"upper|大寫字元|  
|"xdigit"|數字、'a'、'b'、'c'、'd'、'e'、'f'、'A'、'B'、'C'、'D'、'E'、'F'|  
|"d"|與 digit 相同|  
|"s"|與 space 相同|  
|"w"|與 alnum 相同|  
  
### <a name="character-range"></a>字元範圍  
 括號運算式中的字元範圍會將範圍中的所有字元加入至括號運算式所定義的字元集。 若要建立字元範圍，請將字元 '-' 放在範圍中的第一個和最後一個字元之間。 這麼做會將數值大於或等於第一個字元數值，以及小於或等於最後一個字元數值的所有字元放入集合中。 請注意，這組加入的字元取決於平台特定的字元表示。 如果字元 '-' 出現在括號運算式開頭或結尾，或者為字元範圍的第一個或最後一個字元，它表示自己。  
  
 例如：  
  
-   "[0-7]" 表示字元集 { '0', '1', '2', '3', '4', '5', '6', '7' }。 它符合目標序列 "0"、"1" 等等，但不符合 "a"。  
  
-   在使用 ASCII 字元編碼的系統，"[h-k]" 表示字元集 { 'h', 'i', 'j', 'k' }。 它符合目標序列 "h"、"i" 等等，但不符合 "\x8A" 或 "0"。  
  
-   在使用 EBCDIC 字元編碼的系統，"[h-k]" 表示字元集 { 'h', 'i', '\x8A', '\x8B', '\x8C', '\x8D', '\x8E', '\x8F', '\x90', 'j', 'k' } ('h' 編碼為 0x88，而 'k' 編碼為 0x92)。 它符合目標序列 "h"、"i"、"\x8A" 等等，但不符合 "0"。  
  
-   "[-0-24]" 表示字元集 { '-', '0', '1', '2', '4' }。  
  
-   "[0-2-]" 表示字元集 { '0', '1', '2', '-' }。  
  
-   在使用 ASCII 字元編碼的系統，"[+--]" 表示字元集 { '+', ',', '-' }。  
  
 不過，當使用區分地區設定的範圍時，範圍中的字元取決於地區設定的定序規則。 在範圍定義中第一個字元後定序的字元，以及在範圍定義中最後一個字元前定序的字元是在這個集合中。 兩個結尾字元也在這個集合中。  
  
### <a name="collating-element"></a>定序項目  
 定序項目是視為單一字元的多字元序列。  
  
### <a name="collating-symbol"></a>定序符號  
 括號運算式中的定序符號會將「定序項目」加入至括號運算式所定義的集合。 若要建立定序符號，請使用 "[."， 後面接著定序項目，然後再接著 ".]"。  
  
### <a name="control-escape-sequence"></a>控制項逸出序列  
 控制項逸出序列是反斜線，後面接著字母 'c'，後面接著 'a' 到 'z' 或 'A' 到 'Z' 其中一個字母。 它符合由該字元所指名的 ASCII 控制字元。 例如，"\ci" 符合目標序列 "\x09"，因為 \<ctrl-i> 的值為 0x09。  
  
### <a name="dsw-character-escape"></a>DSW 逸出字元  
 DSW 逸出字元是字元類別的簡短名稱，如下表所示。  
  
|逸出序列|對等具名類別|預設具名類別|  
|---------------------|----------------------------|-------------------------|  
|"\d"|"[[:d:]]"|"[[:digit:]]"|  
|"\D"|"[^[:d:]]"|"[^[:digit:]]"|  
|"\s"|"[[:s:]]"|"[[:space:]]"|  
|"\S"|"[^[:s:]]"|"[^[:space:]]"|  
|"\w"|"[[:w:]]"|"[a-zA-Z0-9_]"*|  
|"\W"|"[^[:w:]]"|"[^a-zA-Z0-9_]"*|  
  
 *ASCII 字元集  
  
### <a name="equivalence-class"></a>等價類別  
 括號運算式中的等價類別會將相當於等價類別定義中之定序項目的所有字元及「定序項目」加入至括號運算式所定義的集合。 若要建立等價類別，請使用 "[="，後面接著定序項目，後面接著 "=]"。 在內部，如果 `elt1`，則兩個定序項目 `elt2` 和 `traits.transform_primary(elt1.begin(), elt1.end()) == traits.transform_primary(elt2.begin(), elt2.end())` 相等。  
  
### <a name="file-format-escape"></a>檔案格式逸出  
 檔案格式逸出是由一般的 C 語言字元逸出序列 "\\\\"、"\a"、"\b"、"\f"、"\n"、"\r"、"\t"、"\v" 所組成。這些具有一般意義，也就是分別為反斜線、警示、退格鍵、換頁字元、新行字元、歸位字元、水平索引標籤和垂直索引標籤。 在 `ECMAScript`，不允許 "\a" 和 "\b"  (允許 "\\\\"，但它是識別逸出，而非檔案格式逸出)。  
  
### <a name="hexadecimal-escape-sequence"></a>十六進位逸出序列  
 十六進位逸出序列是反斜線，後面接著字元 'x'，後面接著兩個十六進位數字 (0-9a-fA-F)。 它符合目標序列中值由兩個數字指定的字元。 例如，當使用 ASCII 字元編碼時，"\x41" 符合目標序列 "A"。  
  
### <a name="identity-escape"></a>識別逸出  
 識別逸出為反斜線，後面接著單一字元。 它符合該字元。 當字元有特殊意義時，需要識別逸出；透過使用識別逸出，移除特殊意義。 例如:   
  
-   "a*" 符合目標序列 "aaa"，但不符合目標序列 "a\*"。  
  
-   "a\\*" 不符合目標序列 "aaa"，但符合目標序列 "a\*"。  
  
 識別逸出中允許的一組字元取決於規則運算式文法，如下表所示。  
  
|文法|允許的識別逸出字元|  
|-------------|----------------------------------------|  
|`basic`, `grep`|{ '(', ')', '{', '}', '.', '[', '\\', '*', '^', '$' }|  
|`extended`, `egrep`|{ '(', ')', '{', '.', '[', '\\', '*', '^', '$', '+', '', '&#124;' }|  
|`awk`|`extended` 加上 { '"', '/' }|  
|`ECMAScript`|所有字元，但可以是識別項一部分的字元除外。 通常，這包括字母、數字、'$'、'_' 和 Unicode 逸出序列。 如需詳細資訊，請參閱＜ECMAScript 語言規格＞。|  
  
### <a name="individual-character"></a>個別字元  
 括號運算式中的個別字元會將該字元加入至括號運算式所定義的字元集。 除了括號運算式開頭的任何位置，'^' 代表自己。  
  
 例如：  
  
-   "[abc]" 符合目標序列 "a"、"b" 和 "c"，但不符合序列 "d"。  
  
-   "[^abc]" 符合目標序列 "d"，但不符合目標序列 "a"、"b" 或 "c"。  
  
-   "[a^bc]" 符合目標序列 "a"、"b"、"c" 和 "^"，但不符合目標序列 "d"。  
  
 在所有規則運算式文法 (`ECMAScript` 除外)，如果 ']' 是左括號 '[' 後面的第一個字元或是初始 '^' 後面的第一個字元，它表示自己。  
  
 例如：  
  
-   "[]a" 無效，因為沒有 ']' 結束括號運算式。  
  
-   "[]abc]" 符合目標序列 "a"、"b"、"c" 和 "]"，但不符合目標序列 "d"。  
  
-   "[^]abc]" 符合目標序列 "d"，但不符合目標序列 "a"、"b"、"c" 或 "]"。  
  
 在 `ECMAScript` 中，使用 '\\]' 來代表括號運算式中的字元 ']'。  
  
 範例：  
  
-   "[]a" 符合目標序列 "a"，因為括號運算式為空白。  
  
-   "[\\]abc]" 符合目標序列 "a"、"b"、"c" 和 "]"，但不符合目標序列 "d"。  
  
### <a name="negative-assert"></a>負判斷提示  
 負判斷提示符合任何項目，但其內容除外。 它不會使用目標序列中的任何字元。 例如，"(!aa)(a*)" 符合目標序列 "a"，並將擷取群組 1 關聯至子序列 "a"。 它不符合目標序列 "aa" 或目標序列 "aaa"。  
  
### <a name="negative-word-boundary-assert"></a>負字邊界判斷提示  
 如果目標字串中的目前位置不是緊接在「字邊界」之後，負字邊界判斷提示就會相符。  
  
### <a name="non-capture-group"></a>非擷取群組  
 非擷取群組將其內容標記為規則運算式文法中的單一單位，但不會標記目標文字。 例如，"(a)(:b)*(c) 符合目標序列 "abbc"，並將擷取群組 1 關聯至子序列 "a"，以及將擷取群組 2 關聯至子序列 "c"。  
  
### <a name="non-greedy-repetition"></a>非窮盡重複  
 非窮盡重複使用目標序列中符合模式的最短子序列。 窮盡重複使用最長子序列。 例如，"(a+)(a*b)" 符合目標序列 "aaab"。 使用非窮盡重複時，它會將擷取群組 1 與目標序列開頭的子序列 "a" 關聯，並將擷取群組 2 與目標序列結尾的子序列 "aab" 關聯。 使用窮盡重複時，它會將擷取群組 1 與子序列 "aaa" 關聯，並將擷取群組 2 與子序列 "b" 關聯。  
  
### <a name="octal-escape-sequence"></a>八進位逸出序列  
 八進位逸出序列是反斜線，後面接著一個、兩個或三個八進位數字 (0-7)。 它符合目標序列中值由這些數字指定的字元。 如果所有數字都是 '0'，序列無效。 例如，當使用 ASCII 字元編碼時，"\101" 符合目標序列 "A"。  
  
### <a name="ordinary-character"></a>一般字元  
 一般字元是目前文法中沒有特殊意義的任何有效字元。  
  
 在 `ECMAScript` 中，下列字元有特殊意義：  
  
-   ^  $  \  .  *  +    (  )  [  ]  {  }  &#124;  
  
 在 `basic` 和 `grep` 中，下列字元有特殊意義：  
  
-   .   [   \  
  
 此外，在 `basic` 和 `grep`，下列字元於特定內容中使用時有特殊意義：  
  
-   '*' 在所有案例中都有特殊意義，除非它是規則運算式中的第一個字元或是規則運算式中初始 '^' 後面的第一個字元，或者它是擷取群組的第一個字元或是擷取群組中初始 '^' 後面的第一個字元。  
  
-   當 '^' 是規則運算式的第一個字元時，它具有特殊意義。  
  
-   當 '$' 是規則運算式的最後一個字元時，它具有特殊意義。  
  
 在 `extended`、`egrep` 和 `awk` 中，下列字元有特殊意義：  
  
-   。   [   \   (   *   +      {   &#124;  
  
 此外，在 `extended`、`egrep` 和 `awk`，下列字元於特定內容中使用時有特殊意義。  
  
-   當 ')' 有對應的前面 '(' 時，它有特殊意義。  
  
-   當 '^' 是規則運算式的第一個字元時，它具有特殊意義。  
  
-   當 '$' 是規則運算式的最後一個字元時，它具有特殊意義。  
  
 一般字元符合目標序列中的相同字元。 根據預設，這表示如果兩個字元是由相同的值表示，比對成功。 在不區分大小寫的比對，如果 `ch0`，兩個字元 `ch1` 和 `traits.translate_nocase(ch0) == traits.translate_nocase(ch1)` 相符。 在區分地區設定的比對，如果 `ch0`，兩個字元 `ch1` 和 `traits.translate(ch0) == traits.translate(ch1)` 相符。  
  
### <a name="positive-assert"></a>正判斷提示  
 正判斷提示符合其內容，但不使用目標序列中的任何字元。  
  
 範例：  
  
-   "(=aa)(a*)" 符合目標序列 "aaaa"，並將擷取群組 1 關聯至子序列 "aaaa"。  
  
-   "(aa)(a*)" 符合目標序列 "aaaa"，而且會將擷取群組 1 與目標序列開頭的子序列 "aa" 關聯，並將擷取群組 2 與目標序列結尾的子序列 "aa" 關聯。  
  
-   "(=aa)(a)&#124;(a)" 符合目標序列 "a"，並將擷取群組 1 關聯至空序列 (因為正判斷提示失敗)，以及將擷取群組 2 關聯至子序列 "a"。 它也符合目標序列 "aa"，而且會將擷取群組 1 與子序列 "aa"，並將擷取群組 2 與空序列關聯。  
  
### <a name="unicode-escape-sequence"></a>Unicode 逸出序列  
 Unicode 逸出序列是反斜線，後面接著字元 'u'，後面接著四個十六進位數字 (0-9a-fA-F)。 這符合其值由四個數字指定之目標序列中的字元。 例如，當使用 ASCII 字元編碼時，"\u0041" 符合目標序列 "A"。  
  
### <a name="wildcard-character"></a>萬用字元  
 萬用字元符合目標運算式中新行字元以外的任何字元。  
  
### <a name="word-boundary"></a>字邊界  
 在下列情況下，會出現字邊界：  
  
-   目前字元是在目標序列開頭，而且是文字字元 `A-Za-z0-9_.` 其中一個。  
  
-   目前字元位置超過目標序列結尾，而且目標序列中的最後一個字元是其中一個文字字元。  
  
-   目前字元是其中一個文字字元，而且前一個字元不是。  
  
-   目前字元不是其中一個文字字元，而且前一個字元是。  
  
### <a name="word-boundary-assert"></a>字邊界判斷提示  
 若目標字串中的目前位置緊接在「字邊界」之後，字邊界判斷提示就會相符。  
  
##  <a name="matchingandsearching"></a> 比對和搜尋  
 若要讓規則運算式符合目標序列，整個規則運算式必須符合整個目標序列。 例如，規則運算式 "bcd" 符合目標序列 "bcd"，但不符合目標序列 "abcd" 也不符合目標序列 "bcde"。  
  
 若要讓規則運算式搜尋成功，目標序列中某處必須有符合規則運算式的子序列。 搜尋通常會尋找最左邊相符的子序列。  
  
 例如：  
  
-   在目標序列 "bcd" 中搜尋規則運算式 "bcd" 成功且符合整個序列。 在目標序列 "abcd" 中相同的搜尋也成功，而且符合最後三個字元。 在目標序列 "bcde" 中相同的搜尋也成功，而且符合前三個字元。  
  
-   在目標序列 "bcdbcd" 中搜尋規則運算式 "bcd" 成功，而且符合前三個字元。  
  
 如果目標序列中某處有多個相符的子序列，有兩種方式選擇符合模式。 當規則運算式相符時，「第一個相符」會選擇第一個找到的子序列。 「最長相符」會從該位置上相符的子序列中選擇最長的子序列。 如果有多個最大長度的子序列，最長相符會選擇第一個找到的子序列。 例如，使用第一個相符時，在目標序列 "abcd" 中搜尋規則運算式 "b&#124;bc" 會符合子序列 "b"，由於替代的左方詞彙符合該子序列，因此第一個相符不會嘗試使用替代的右方詞彙。 當使用最長相符時，相同的搜尋符合 "bc"，因為 "bc" 比 "b" 長。  
  
 如果比對達到目標序列結尾而未失敗，即使尚未達到規則運算式的結尾，部分符合仍成功。 因此，在部分符合成功後，將字元附加至目標序列可能造成後續部分符合失敗。 不過，在部分符合失敗後，將字元附加至目標序列不會造成後續部分符合成功。 例如，使用部分相符時，"ab" 符合目標序列 "a"，但不符合 "ac"。  
  
##  <a name="formatflags"></a> 格式旗標  
  
|ECMAScript 格式規則|sed 格式規則|取代文字|  
|-----------------------------|----------------------|----------------------|  
|"$&"|"&"|符合整個規則運算式的字元序列 (`[match[0].first, match[0].second)`)|  
|"$$"||"$"|  
||"\\&"|"&"|  
|"$`" (貨幣符號，後面接著反引號)||在符合規則運算式的子序列之前的字元序列 (`[match.prefix().first, match.prefix().second)`)|  
|"$'" (貨幣符號，後面接著正引號)||在符合規則運算式的子序列之後的字元序列 (`[match.suffix().first, match.suffix().second)`)|  
|"$n"|"\n"|符合位置之擷取群組的字元序列`n`，其中`n`是介於 0 到 9 的數字 (`[match[n].first, match[n].second)`)|  
||"\\\n"|"\n"|  
|"$nn"||符合位置之擷取群組的字元序列`nn`，其中`nn`是介於 10 到 99 之間的數字 (`[match[nn].first, match[nn].second)`)|  
  
## <a name="see-also"></a>另請參閱  
 [C++ 標準程式庫概觀](../standard-library/cpp-standard-library-overview.md)

