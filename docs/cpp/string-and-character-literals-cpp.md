---
title: "字串和字元常值 (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "R"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "逸出序列"
  - "L 常數"
  - "常值字串"
  - "常值字串, C++"
  - "Null 字串"
  - "Null 字串, 以 null 結尾的字串"
  - "NULL, 字元常數"
  - "字串常值"
  - "字串常值, 語法"
  - "字串 [C++], 字串常值"
  - "寬字元, 字串"
ms.assetid: 61de8f6f-2714-4e7b-86b6-a3f885d3b9df
caps.latest.revision: 36
caps.handback.revision: 34
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 字串和字元常值 (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ 支援各種字串和字元類型，並提供方法來表示所有這些類型的常值。 在原始程式碼中，您可以使用字元集表示字元和字串常值的內容。 通用字元名稱和逸出字元允許您只使用基本來源字元集表示任何字串。 原始字串常值可讓您避免使用逸出字元，而且可用來表示所有類型的字串常值。 您也可以建立 std::string 常值，不必執行額外的建構或轉換步驟。  
  
```cpp  
#include <string> using namespace std::string_literals; // enables s-suffix for std::string literals int main() { // Character literals auto c0 =   'A'; // char auto c1 = u8'A'; // char auto c2 =  L'A'; // wchar_t auto c3 =  u'A'; // char16_t auto c4 =  U'A'; // char32_t // String literals auto s0 =   "hello"; // const char* auto s1 = u8"hello"; // const char*, encoded as UTF-8 auto s2 =  L"hello"; // const wchar_t* auto s3 =  u"hello"; // const char16_t*, encoded as UTF-16 auto s4 =  U"hello"; // const char32_t*, encoded as UTF-32 // Raw string literals containing unescaped \ and " auto R0 =   R"("Hello \ world")"; // const char* auto R1 = u8R"("Hello \ world")"; // const char*, encoded as UTF-8 auto R2 =  LR"("Hello \ world")"; // const wchar_t* auto R3 =  uR"("Hello \ world")"; // const char16_t*, encoded as UTF-16 auto R4 =  UR"("Hello \ world")"; // const char32_t*, encoded as UTF-32 // Combining string literals with standard s-suffix auto S0 =   "hello"s; // std::string auto S1 = u8"hello"s; // std::string auto S2 =  L"hello"s; // std::wstring auto S3 =  u"hello"s; // std::u16string auto S4 =  U"hello"s; // std::u32string // Combining raw string literals with standard s-suffix auto S5 =   R"("Hello \ world")"s; // std::string from a raw const char* auto S6 = u8R"("Hello \ world")"s; // std::string from a raw const char*, encoded as UTF-8 auto S7 =  LR"("Hello \ world")"s; // std::wstring from a raw const wchar_t* auto S8 =  uR"("Hello \ world")"s; // std::u16string from a raw const char16_t*, encoded as UTF-16 auto S9 =  UR"("Hello \ world")"s; // std::u32string from a raw const char32_t*, encoded as UTF-32 }  
```  
  
 字串常值可以沒有前置詞，或者以 `u8`、`L`、`u` 和 `U` 前置詞分別表示半形字元 \(單一位元組或多位元組\)、UTF\-8、全形字元 \(UCS\-2 或 UTF\-16\)、UTF\-16 和 UTF\-32 編碼。 原始字串常值可以有 `R`、`u8R`、`LR`、`uR` 和 `UR` 前置詞，相當於這些編碼方式的原始版本。  若要建立暫存或靜態的 std::string 值，字串常值或原始字串常值可以搭配使用 `s` 後置詞。 如需詳細資訊，請參閱下節的＜字串常值＞。 如需基本原始程式碼字元集、通用字元名稱，以及使用原始程式碼擴充字碼頁字元的詳細資訊，請參閱 [字元集](../cpp/character-sets2.md)。  
  
## 字元常值  
 *「字元常值」*\(character literal\) 是由常數字元所組成。 其表示方式是以單引號括住字元。 字元常值有四種類型：  
  
-   `char` 類型的半形字元常值，例如 `'a'`  
  
-   `wchar_t` 類型的全形字元常值，例如 `L'a'`  
  
-   `char16_t` 類型的全形字元常值，例如 `u'a'`  
  
-   `char32_t` 類型的全形字元常值，例如 `U'a'`  
  
 用於字元常值的字元可以是任何字元，但保留字元反斜線 \('\\'\)、單引號 \('\) 或新行字元除外。 使用逸出序列可指定保留字元。 只要類型大到足以容納字元，就可以使用通用字元名稱指定字元。  
  
###  <a name="bkmk_Escape"></a> 逸出序列  
 逸出序列有三種：簡單的、八進位和十六進位。 逸出序列可以是下列任何一項：  
  
|值|逸出序列|值|逸出序列|  
|-------|----------|-------|----------|  
|新行字元|\\n|反斜線|\\\\|  
|水平定位字元|\\t|問號|? 或 \\?|  
|垂直定位字元|\\v|單引號|\\'|  
|退格鍵|\\b|雙引號|\\"|  
|歸位字元|\\r|null 字元|\\0|  
|換頁字元|\\f|八進位|\\ooo|  
|警示 \(鈴聲\)|\\a|十六進位|\\xhhh|  
  
 下列程式碼顯示一些使用半形字串常值的逸出字元範例。 相同的語法適用於其他字串常值類型。  
  
```cpp  
#include <iostream> using namespace std; int main() { char newline = '\n'; char tab = '\t'; char backspace = '\b'; char backslash = '\\'; char nullChar = '\0'; cout << "Newline character: " << newline << "ending" << endl; // Newline character: //  ending cout << "Tab character: " << tab << "ending" << endl; // Tab character : ending cout << "Backspace character: " << backspace << "ending" << endl; // Backspace character : ending cout << "Backslash character: " << backslash << "ending" << endl; // Backslash character : \ending cout << "Null character: " << nullChar << "ending" << endl; //Null character:  ending }  
```  
  
 **Microsoft 特定的**  
  
 若要從無前置詞的字元常值建立值，編譯器會將單引號間的字元或字元順序轉換成 32 位元整數內的 8 位元值。 常值中的多個字元，會視需要從高序位到低序位填入對應的位元組。 若要建立 `char` 值，編譯器會採用低序位位元組。 若要建立 `wchar_t` 或  `char16_t` 值，編譯器會採用低序位字組。 如果任何位元設定高出指定的位元組或字組，編譯器會警告結果遭截斷。  
  
```cpp  
char c0    = 'abcd';    // C4305, C4309, truncates to 'd' wchar_t w0 = 'abcd';    // C4305, C4309, truncates to '\x6364'  
```  
  
 八進位逸出序列是反斜線，後面接著最多 3 個八進位數字的序列。 可能包含超過三位數的八進位逸出序列，其行為會被視為 3 位數八進位序列，後面跟著的數字視為字元，其結果會令人大出意外。 例如：  
  
```cpp  
char c1 = '\100';   // '@' char c2 = '\1000';  // C4305, C4309, truncates to '0'   
```  
  
 可能包含非八進位字元的逸出序列，一直到最後一個八進位的字元都會評估為八進位序列，後面則視為其餘字元。 例如：  
  
```cpp  
char c3 = '\009';   // '9' char c4 = '\089';   // C4305, C4309, truncates to '9' char c5 = '\qrs';   // C4129, C4305, C4309, truncates to 's'  
```  
  
 十六進位逸出序列是反斜線，後面接著字元 `x`，後面接著十六進位數字序列。 不包含十六位元數字的逸出序列會造成編譯器錯誤 C2153：「十六進位常值至少必須有一個十六進位數字」。 系統會忽略前置零。 可能有十六進位和非十六進位字元的逸出序列，一直到最後一個十六進位的字元都會評估為十六進位逸出序列，後面則視為非十六進位字元。   在沒有前置詞或 u8 前置詞的半形字元常值中，最高的十六進位值是 0xFF。 在 L 前置詞或 u 前置詞的全形字元常值中，最高的十六進位值是 0xFFFF。 在 U 前置詞的全形字元常值中，最高的十六進位值是 0xFFFFFFFF。  
  
```cpp  
char c6 = '\x0050'; // 'P' char c7 = '\x0pqr'; // C4305, C4309, truncates to 'r'  
```  
  
 如果全形字元常值前面加上包含多個字元的 `L`，會從第一個字元拿掉此值。 忽略後續的字元，與對等無前置詞的半形字元常值行為不同。  
  
```cpp  
wchar_t w1 = L'\100';   // L'@' wchar_t w2 = L'\1000';  // C4066 L'@', 0 ignored wchar_t w3 = L'\009';   // C4066 L'\0', 9 ignored wchar_t w4 = L'\089';   // C4066 L'\0', 89 ignored wchar_t w5 = L'\qrs';   // C4129, C4066 L'q' escape, rs ignored wchar_t w6 = L'\x0050'; // L'P' wchar_t w7 = L'\x0pqr'; // C4066 L'\0', pqr ignored  
```  
  
 **END Microsoft 特定的**  
  
 當放置在一行的結尾時，反斜線字元 \(\\\) 就是行接續字元。 如果您想要讓反斜線字元顯示為字元常值，您必須輸入連續的兩個反斜線 \(`\\`\)。 如需行接續字元的詳細資訊，請參閱 [轉譯階段](../preprocessor/phases-of-translation.md)。  
  
###  <a name="bkmk_UCN"></a> 通用字元名稱  
 在字元常值和原生 \(非原始\) 的字串常值中，任何字元都可能使用通用字元名稱表示。  通用字元名稱的格式為前置詞 \\U 加上八位數的 Unicode 字碼指標，或是前置詞 \\u 加上四位數的 Unicode 字碼指標。 所有的八位數或四位數，都一定要出現才是格式正確的通用字元名稱。  
  
```cpp  
char u1 = 'A';          // 'A' char u2 = '\101';       // octal, 'A' char u3 = '\x41';       // hexadecimal, 'A' char u4 = '\u0041';     // \u UCN 'A' char u5 = '\U00000041'; // \U UCN 'A'  
```  
  
 **Surrogate 字組**  
  
 通用字元名稱無法編碼在 surrogate 字碼指標範圍 D800\-DFFF 內的值。 至於 Unicode surrogate 字組，請使用 `\UNNNNNNNN` 指定通用字元名稱，這裡的 NNNNNNNN 為字元的八位數字碼指標。 如有需要，編譯器會產生 surrogate 字組。  
  
 過去在 C\+\+03 中，語言只允許由其通用字元名稱所代表的字元子集，以及未實際代表任何有效 Unicode 字元的一些通用字元名稱。 這已在 C\+\+11 標準中修正。 在 C\+\+11 中，字元和字串常值及識別項可以使用通用字元名稱。  如需通用字元名稱的詳細資訊，請參閱 [字元集](../cpp/character-sets2.md)。 如需 Unicode 的詳細資訊，請參閱 [Unicode](http://msdn.microsoft.com/library/dd374081\(v=vs.85\).aspx)。 如需 Surrogate 字組的詳細資訊，請參閱 [Surrogate 字組和補充字元](http://msdn.microsoft.com/library/dd374069\(v=vs.85\).aspx)。  
  
## 字串常值  
 字串常值代表構成 null 結束字串的一連串字元。 這些字元必須使用雙引號括起來。 有下列字串常值類型：  
  
### 半形字串常值  
 半形字串常值是非前置詞、雙引號分隔的、以 null 結束陣列類型的 `const` `char`\[`n`\]，這裡的 n 是以位元組為單位的陣列長度。 半形字串常值可能包含任何圖形字元，但雙引號 \(`"`\)、反斜線 \(`\`\) 或新行字元除外。 半形字串常值也可能包含上文列出的逸出序列，以及符合一個位元組大小的通用字元名稱。  
  
```cpp  
const char *narrow = "abcd"; // represents the string: yes\no const char *escaped = "yes\\no";  
```  
  
 **UTF\-8 編碼的字串**  
  
 UTF\-8 編碼的字串是 u8 前置詞、雙引號分隔、null 結束陣列類型的 `const` `char`\[`n`\]，這裡的 n 是以位元組為單位的編碼陣列長度。 u8 前置字串常值可以包含任何圖形字元，但雙引號 \(`"`\)、反斜線 \(`\`\) 或新行字元除外。 u8 前置字串常值也可以包含上列逸出序列，以及任何通用字元名稱。  
  
```cpp  
const char* str1 = u8"Hello World"; const char* str2 = u8"\U0001F607 is O:-)";  
```  
  
### 全形字串常值  
 全形字串常值是前面加上 '`L`' 且包含任何圖形字元 \(雙引號 \("\)、反斜線 \(\\\) 或新行字元以外\) 的 null 結束 `wchar_t` 常數陣列。 全形字串常值可以包含上列逸出序列，以及任何通用字元名稱。  
  
```cpp  
const wchar_t* wide = L"zyxw"; const wchar_t* newline = L"hello\ngoodbye";  
```  
  
 **char16\_t 和 char32\_t \(C\+\+11\)**  
  
 C\+\+11 引進可攜式 `char16_t` \(16 位元 Unicode\) 和 `char32_t` \(32 位元 Unicode\) 字元類型：  
  
```cpp  
auto s3 = u"hello"; // const char16_t* auto s4 = U"hello"; // const char32_t*  
```  
  
### 原始字串常值 \(C\+\+11\)  
 原始字串常值是 null 結束陣列 \(為任意字元類型\)，其中包含任何圖形字元 \(包括雙引號 \("\)、反斜線 \(\\\) 或新行字元\)。 原始字串常值通常用於使用字元類別的規則運算式，以及 HTML 字串和 XML 字串。 如需範例，請參閱下列文章：[Bjarne Stroustrup 的 C\+\+11 常見問題集](http://go.microsoft.com/fwlink/?LinkId=401172)。  
  
```cpp  
// represents the string: An unescaped \ character const char* raw_narrow = R"(An unescaped \ character)"; const wchar_t* raw_wide = LR"(An unescaped \ character)"; const char*       raw_utf8  = u8R"(An unescaped \ character)"; const char16_t* raw_utf16 = uR"(An unescaped \ character)"; const char32_t* raw_utf32 = UR"(An unescaped \ character)";  
```  
  
 分隔符號是使用者定義的順序，最多包含 16 個字元，在原始字串常值的左括號前面、右括號後面。  例如，`R"abc(Hello"\()abc"` 中的分隔符號順序是 `abc`，字串內容是 `Hello"\(`。 您可以使用分隔符號，釐清包含雙引號和括號的原始字串。 這會造成編譯器錯誤：  
  
```cpp  
// meant to represent the string: )” const char* bad_parens = R"()")";  // error C2059  
```  
  
 但是分隔符號解決這個錯誤：  
  
```cpp  
const char* good_parens = R"xyz()")xyz";  
```  
  
 您可以在來源中建構有新行字元 \(不是逸出字元\) 的原始字串常值：  
  
```cpp  
// represents the string: hello //goodbye const wchar_t* newline = LR"(hello goodbye)";  
```  
  
### std::string 常值 \(C\+\+14\)  
 std::string 常值是呈現為 "xyx"s \(後置詞為 `s`\) 之使用者定義常值的標準程式庫實作 \(請參閱下文\)。 這種類型的字串常值會根據指定的前置詞來產生類型 std::string、std::wstring、std::u32string 或 std::u16string 的暫存物件。 未使用前置詞時 \(如上所述\)，會產生 std::string。 L"xyz"s 會產生 std::wstring。 u"xyz"s 會產生 [std::u16string](../Topic/u16string.md)，U"xyz"s 則會產生 [std::u32string](../Topic/u32string.md)。  
  
```cpp  
//#include <string> //using namespace std::string_literals; string str{ "hello"s }; string str2{ u8"Hello World" }; wstring str3{ L"hello"s }; u16string str4{ u"hello"s }; u32string str5{ U"hello"s };  
```  
  
 s 後置詞也可以用於原始字串常值：  
  
```cpp  
u32string str6{ UR"(She said "hello.")"s };  
```  
  
 std::string 常值定義於 \<string\> 標頭檔的命名空間 `std::literals::string_literals` 中。 因為 `std::literals::string_literals`，而且 `std::literals` 都宣告為[內嵌命名空間](../cpp/namespaces-cpp.md)，所以會自動將 `std::literals::string_literals` 視為直接屬於命名空間 `std`。  
  
### 字串常值的大小  
 對於 ANSI char\* 字串和其他單一位元組的編碼 \(非 UTF\-8\)，字串常值的大小 \(位元組\) 是字元數加 1 \(表示結束 null 字元\)。 對於所有其他字串類型，嚴格上，大小未與字元數相關。 UTF\-8 使用最多四個字元項目來編碼部分*「程式碼單位」*\(Code Unit\)，而編碼為 UTF\-16 的 char16\_t 或 wchar\_t 可能會使用兩個項目 \(共有四個位元組\) 來編碼單一*「程式碼單位」*\(Code Unit\)。   本例顯示全形字串常值以位元組為單位的大小：  
  
```cpp  
const wchar_t* str = L"Hello!"; const size_t byteSize = (wcslen(str) + 1) * sizeof(wchar_t);  
```  
  
 請注意，`strlen()` 和 `wcslen()` 不包括結束 null 字元的大小，其大小等於字串類型的項目大小：char\* 字串上的一個位元組、wchar\_t\* 或 char16\_t\* 字串上的兩個位元組，以及 char32\_t\* 字串上的四個位元組。  
  
 字串常值的長度上限為 65535 個位元組。 這個限制適用於半形字串常值和全形字串常值。  
  
### 修改字串常值  
 由於字串常值 \(不包括 std:string 常值\) 是常數，因此嘗試加以修改 \(例如 str\[2\] \= 'A'\) 會造成編譯器錯誤。  
  
 **Microsoft 特定的**  
  
 在 Visual C\+\+ 中，您可以使用字串常值，初始化非常數 `char` 或 `wchar_t` 的指標。 C99 程式碼允許這項功能，不過在 C\+\+98 中已被取代，在 C\+\+11 中已移除。 嘗試修改字串造成存取違規，如此範例所示：  
  
```cpp  
wchar_t* str = L"hello"; str[2] = L'a'; // run-time error: access violation  
```  
  
 當您設定 [\/Zc:strictStrings \(停用字串常值型別轉換\)](../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) 編譯器選項時，您可以讓編譯器在字串常值轉換為 non\_const 字元指標時發出錯誤。 我們建議使用標準相容的可攜式程式碼。 使用 `auto` 關鍵字，宣告字串常值初始化的指標，也是不錯的做法，因為這會解析成正確 \(常數\) 類型。 例如，這個程式碼範例會攔截在編譯時期嘗試寫入字串常值的動作：  
  
```cpp  
auto str = L"hello"; str[2] = L'a'; // C3892: you cannot assign to a variable that is const.  
```  
  
 在某些情況下，可以結合相同字串常值來節省可執行檔中的空間。 在字串常值共用中，編譯器會讓特定字串常值的所有參考指向記憶體內部相同位置，而不是讓每個參考都指向字串常值的個別執行個體。 若要啟用字串共用，請使用 [\/GF](../build/reference/gf-eliminate-duplicate-strings.md) 編譯器選項。  
  
 **結束 Microsoft 專有**  
  
### 串連相鄰的字串常值  
 會串連相鄰的全形或半形字串常值。 這個宣告：  
  
```cpp  
char str[] = "12" "34";  
```  
  
 等同於此宣告：  
  
```cpp  
char atr[] = "1234";  
```  
  
 以及這個宣告：  
  
```cpp  
char atr[] =  "12\ 34";  
```  
  
 使用內嵌十六進位逸出程式碼指定字串常值可能造成未預期的結果。 下列範例是要建立包含 ASCII 5 字元的字串常值，後面接著字元 f、i、v 和 e：  
  
```cpp  
"\x05five"  
```  
  
 實際結果是十六進位 5F \(即底線字元的 ASCII 碼\)，後面接 i、v、e 字元。 若要 取得正確結果，您可以使用其中一個：  
  
```cpp  
"\005five"     // Use octal literal. "\x05" "five"  // Use string splicing.  
```  
  
 std::string 常值 \(因為它們是 std::string 類型\) 可以使用針對 [basic\_string](../standard-library/basic-string-class.md) 類型所定義的 \+ 運算子進行串連。 它們的串連方式也與相鄰字串常值相同。 在這兩種情況下，字串編碼和後置詞必須相符：  
  
```cpp  
auto x1 = "hello" " " " world"; // OK auto x2 = U"hello" " " L"world"; // C2308: disagree on prefix auto x3 = u8"hello" " "s u8"world"s; // OK, agree on prefixes and suffixes auto x4 = u8"hello" " "s u8"world"z; // C3688, disagree on suffixes  
```  
  
### 含通用字元名稱的字串常值  
 原生 \(非原始\) 的字串常值可以使用通用字元名稱來代表任何字元，只要通用字元名稱可以編碼為字串類型中的一或多個字元。  例如，通用字元名稱表示的擴充字元無法編碼在使用 ANSI 字碼頁的半形字串中，但可以編碼在某些多位元組字碼頁的半形字串中，或編碼在 UTF\-8 字串或全形字串中。 在 C\+\+11 中，Unicode 支援已為 char16\_t\* 和 char32\_t\* 字串類型所擴充：  
  
```cpp  
// ASCII smiling face const char*     s1 = ":-)"; // UTF-16 (on Windows) encoded WINKING FACE (U+1F609) const wchar_t*  s2 = L"😉 = \U0001F609 is ;-)"; // UTF-8  encoded SMILING FACE WITH HALO (U+1F607) const char*     s3 = u8"😇 = \U0001F607 is O:-)"; // UTF-16 encoded SMILING FACE WITH OPEN MOUTH (U+1F603) const char16_t* s4 = u"😃 = \U0001F603 is :-D"; // UTF-32 encoded SMILING FACE WITH SUNGLASSES (U+1F60E) const char32_t* s5 = U"😎 = \U0001F60E is B-)";  
```  
  
## 請參閱  
 [字元集](../cpp/character-sets2.md)   
 [數值、布林值和指標常值](../cpp/numeric-boolean-and-pointer-literals-cpp.md)   
 [使用者定義常值](../cpp/user-defined-literals-cpp.md)