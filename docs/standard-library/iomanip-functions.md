---
title: "&lt;iomanip&gt; 函式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iomanip/std::get_money
- iomanip/std::get_time
- iomanip/std::put_money
- iomanip/std::put_time
- iomanip/std::quoted
- iomanip/std::resetiosflags
- iomanip/std::setbase
- iomanip/std::setfill
- iomanip/std::setiosflags
- iomanip/std::setprecision
- iomanip/std::setw
ms.assetid: 3ddde610-70cc-4cfa-8a89-3e83d1d356a8
caps.latest.revision: 10
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: cc990171c1196a35f0fe90d99ee1cbdbca337c9a
ms.contentlocale: zh-tw
ms.lasthandoff: 04/29/2017

---
# <a name="ltiomanipgt-functions"></a>&lt;iomanip&gt; 函式
||||  
|-|-|-|  
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|  
|[put_time](#iomanip_put_time)|[quoted](#quoted)|[resetiosflags](#resetiosflags)|  
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|  
|[setprecision](#setprecision)|[setw](#setw)|  
  
##  <a name="iomanip_get_money"></a>  get_money  
 使用所需的格式從資料流中擷取貨幣值，並在參數中傳回該值。  
  
```  
template <class Money>  
T7 get_money(Money& _Amount, bool _Intl);
```  
  
### <a name="parameters"></a>參數  
 _Amount  
 所擷取的貨幣值。  
  
 _Intl  
 如果為 `true`，便會使用國際格式。 預設值是 `false`。  
  
### <a name="remarks"></a>備註  
 操作工具會傳回一個物件，從資料流 `str` 中擷取此物件時，其行為會像`formatted input function`一樣，此函式會呼叫與 `str` 關聯之地區設定 facet `money_get` 的成員函式 `get`，其中會使用 `_Intl` 來指出使用國際格式。 如果成功，該呼叫就會在 `_Amount` 中儲存所擷取的貨幣值。 接著，操作工具會傳回 `str`。  
  
 `Money` 必須屬於 `long double` 類型，或是元素及特性參數與 `str` 相同之 `basic_string` 的具現化。  
  
##  <a name="iomanip_get_time"></a>  get_time  
 使用所需的格式從資料流中擷取時間值。 在參數中以時間結構的形式傳回值。  
  
```  
template <class Elem>  
T10 put_time(struct tm *_Tptr, const Elem *_Fmt);
```  
  
### <a name="parameters"></a>參數  
 `_Tptr`  
 採用時間結構形式的時間。  
  
 `_Fmt`  
 用來取得時間值的所需格式。  
  
### <a name="remarks"></a>備註  
 操作工具會傳回一個物件，從資料流 `str` 中擷取此物件時，其行為會像`formatted input function`一樣，此函式會呼叫與 `str` 關聯之地區設定 facet `time_get` 的成員函式 `get`，其中會使用 `tptr` 來指出時間結構，以及使用 `fmt` 來指出以 Null 結束之格式字串的開頭。 如果成功，該呼叫就會在時間結構中，儲存與所擷取之任何時間欄位關聯的值。 接著，操作工具會傳回 `str`。  
  
##  <a name="iomanip_put_money"></a>  put_money  
 使用所需的格式將金額插入到資料流中。  
  
```  
template <class Money>  
T8 put_money(const Money& _Amount, bool _Intl);
```  
  
### <a name="parameters"></a>參數  
 `_Amount`  
 要插入到資料流中的金額。  
  
 `_Intl`  
 如果操作工具應該使用國際格式，請設定為 `true`，否則，請設定為 `false`。  
  
### <a name="return-value"></a>傳回值  
 傳回 `str`。  
  
### <a name="remarks"></a>備註  
 操作工具會傳回一個物件，將此物件插入到資料流 `str` 中時，其行為會像已格式化的輸出函式一樣，此函式會呼叫與 `str` 關聯之地區設定 facet `money_put` 的成員函式 `put`。 如果成功，該呼叫就會插入適當格式化的 `amount`，其中會使用 `_Intl` 來指出使用國際格式，以及使用 `str.fill()` 作為填滿元素。 接著，操作工具會傳回 `str`。  
  
 `Money` 必須屬於 `long double` 類型，或是元素及特性參數與 `str` 相同之 `basic_string` 的具現化。  
  
##  <a name="iomanip_put_time"></a>  put_time  
 使用指定的格式將來自時間結構的時間值寫入到資料流中。  
  
```  
template <class Elem>  
T10 put_time(struct tm* _Tptr, const Elem* _Fmt);
```  
  
### <a name="parameters"></a>參數  
 `_Tptr`  
 時間結構中所提供要寫入到資料流中的時間值。  
  
 `_Fmt`  
 寫入時間值時所需的格式。  
  
### <a name="remarks"></a>備註  
 操作工具會傳回一個物件，將此物件插入到資料流 `str` 中時，其行為會像`formatted output function`一樣。 輸出函式會呼叫與 `str` 關聯之地區設定 facet `time_put` 的成員函式 `put`。 輸出函式會使用 `_Tptr` 來指出時間結構，以及使用 `_Fmt` 來指出以 NUL 結束之格式字串的開頭。 如果成功，該呼叫就會插入來自格式字串的常值字串，並轉換來自時間結構的值。 接著，操作工具會傳回 `str`。  
  
##  <a name="quoted"></a>  quoted  
 **(C++14 的新功能)** iostream 操作工具，可允許使用 >> 和 << 運算子，將字串便利地往返傳入和傳出資料流。  
  
```  
quoted(std::string str) // or wstring  
quoted(const char* str) //or wchar_t* 
quoted(std::string str, char delimiter, char escape) // or wide versions  
quoted(const char* str, char delimiter, char escape) // or wide versions  
```  
  
### <a name="parameters"></a>參數  
 `str`  
 std::string, char*、字串常值或原始字串常值，或這當中任何一項的寬版本 (例如 std::wstring, wchar_t\*)。  
  
 `delimiter`  
 使用者指定的字元或寬字元，用作字串開頭和結尾的分隔符號。  
  
 `escape`  
 使用者指定的字元或寬字元，用作字串內逸出序列的逸出字元。  
  
### <a name="remarks"></a>備註  
 請參閱[使用插入運算子和控制格式](../standard-library/using-insertion-operators-and-controlling-format.md)。  
  
### <a name="example"></a>範例  
  這個範例將示範如何使用 `quoted` 與預設分隔符號，及使用縮小字串逸出字元。 同樣支援寬字串。  
  
```cpp  
#include <iostream>  
#include <iomanip>  
#include <sstream>  
  
using namespace std;  
  
void show_quoted_v_nonquoted()  
{  
    // Results are identical regardless of input string type:  
    // string inserted { R"(This is a "sentence".)" }; // raw string literal  
    // string inserted { "This is a \"sentence\"." };  // regular string literal  
    const char* inserted = "This is a \"sentence\".";  // const char*  
    stringstream ss, ss_quoted;  
    string extracted, extracted_quoted;  
  
    ss << inserted;  
    ss_quoted << quoted(inserted);  
  
    cout << "ss.str() is storing       : " << ss.str() << endl;  
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl << endl;  
  
    // Round-trip the strings   
    ss >> extracted;  
    ss_quoted >> quoted(extracted_quoted);  
  
    cout << "After round trip: " << endl;  
    cout << "Non-quoted      : " << extracted << endl;  
    cout << "Quoted          : " << extracted_quoted << endl;  
}  
  
void main(int argc, char* argv[])  
{  
    show_quoted_v_nonquoted();  
  
    // Keep console window open in debug mode.  
    cout << endl << "Press Enter to exit" << endl;  
    string input{};  
    getline(cin, input);  
}  
  
/* Output:  
ss.str() is storing       : This is a "sentence".  
ss_quoted.str() is storing: "This is a \"sentence\"."  
  
After round trip:  
Non-quoted      : This  
Quoted          : This is a "sentence".  
  
Press Enter to exit  
*/  
```  
  
### <a name="example"></a>範例  
  下列範例將示範如何提供分隔符號和/或逸出字元給自訂：  
  
```cpp  
#include <iostream>  
#include <iomanip>  
#include <sstream>  
  
using namespace std;  
  
void show_custom_delimiter()  
{  
    string inserted{ R"("This" "is" "a" "heavily-quoted" "sentence".)" };  
    // string inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };  
    // const char* inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };  
    stringstream ss, ss_quoted;  
    string extracted;  
  
    ss_quoted << quoted(inserted, '*');  
    ss << inserted;  
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl;  
    cout << "ss.str() is storing       : " << ss.str() << endl << endl;  
  
    // Use the same quoted arguments as on insertion.  
    ss_quoted >> quoted(extracted, '*');  
  
    cout << "After round trip: " << endl;  
    cout << "Quoted          : " << extracted << endl;  
  
    extracted = {};  
    ss >> extracted;  
    cout << "Non-quoted      : " << extracted << endl << endl;  
}  
  
void show_custom_escape()  
{  
    string inserted{ R"(\\root\trunk\branch\nest\egg\yolk)" };  
    // string inserted{ "\\\\root\\trunk\\branch\\nest\\egg\\yolk" };  
    stringstream ss, ss_quoted, ss_quoted_custom;  
    string extracted;  
  
    // Use '"' as delimiter and '~' as escape character.  
    ss_quoted_custom << quoted(inserted, '"', '~');  
    ss_quoted << quoted(inserted);  
    ss << inserted;  
    cout << "ss_quoted_custom.str(): " << ss_quoted_custom.str() << endl;  
    cout << "ss_quoted.str()       : " << ss_quoted.str() << endl;  
    cout << "ss.str()              : " << ss.str() << endl << endl;  
  
    // No spaces in this string, so non-quoted behaves same as quoted  
    // after round-tripping.  
}  
  
void main(int argc, char* argv[])  
{  
    cout << "Custom delimiter:" << endl;  
    show_custom_delimiter();  
    cout << "Custom escape character:" << endl;  
    show_custom_escape();  
  
    // Keep console window open in debug mode.  
    cout << endl << "Press Enter to exit" << endl;  
    string input{};  
    getline(cin, input);  
}  
/* Output:  
Custom delimiter:  
ss_quoted.str() is storing: *"This" "is" "a" "heavily-quoted" "sentence".*  
ss.str() is storing       : "This" "is" "a" "heavily-quoted" "sentence".  
  
After round trip:  
Quoted          : "This" "is" "a" "heavily-quoted" "sentence".  
Non-quoted      : "This"  
  
Custom escape character:  
ss_quoted_custom.str(): "\\root\trunk\branch\nest\egg\yolk"  
ss_quoted.str()       : "\\\\root\\trunk\\branch\\nest\\egg\\yolk"  
ss.str()              : \\root\trunk\branch\nest\egg\yolk  
  
Press Enter to exit  
*/  
  
```  
  
##  <a name="resetiosflags"></a>  resetiosflags  
 清除指定的旗標。  
  
```  
T1 resetiosflags(ios_base::fmtflags Mask);
```  
  
### <a name="parameters"></a>參數  
 `Mask`  
 要清除的旗標。  
  
### <a name="return-value"></a>傳回值  
 操作工具會傳回一個物件，從資料流 **str** 中擷取此物件或將其插入到該資料流時，會呼叫 **str**. [setf](../standard-library/ios-base-class.md#setf)( `ios_base::`[fmtflags](../standard-library/ios-base-class.md#fmtflags), _ *Mask*)，然後傳回 **str**。  
  
### <a name="example"></a>範例  
  如需使用 `resetiosflags` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。  
  
##  <a name="setbase"></a>  setbase  
 設定整數的基底。  
  
```  
T3 setbase(int _Base);
```  
  
### <a name="parameters"></a>參數  
 `_Base`  
 數字基底。  
  
### <a name="return-value"></a>傳回值  
 操作工具會傳回一個物件，從資料流 **str** 中擷取此物件或將其插入到該資料流時，會呼叫 **str**. `setf`( **mask**, [ios_base::basefield](../standard-library/ios-base-class.md#fmtflags))，然後傳回 **str**。 此處的 **mask** 是以下列方式決定：  
  
-   如果 _ *Base* 為 8，則 **mask** 為 `ios_base::`[oct](../standard-library/ios-functions.md#oct)。  
  
-   如果 _ *Base* 為 10，則 mask 為 `ios_base::`[dec](../standard-library/ios-functions.md#dec)。  
  
-   如果 _ *Base* 為 16，則 **mask** 為 `ios_base::`[hex](../standard-library/ios-functions.md#hex)。  
  
-   如果 _ *Base* 是任何其他值，則 mask 為 `ios_base::`[fmtflags](../standard-library/ios-base-class.md#fmtflags)(0)。  
  
### <a name="example"></a>範例  
  如需使用 `setbase` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。  
  
##  <a name="setfill"></a>  setfill  
 設定將用來填滿靠右對齊顯示中的空格字元。  
  
```  
template <class Elem>  
T4 setfill(Elem Ch);
```  
  
### <a name="parameters"></a>參數  
 `Ch`  
 將用來填滿靠右對齊顯示中空格的字元。  
  
### <a name="return-value"></a>傳回值  
 範本操作工具會傳回一個物件，從資料流 **str** 中擷取此物件或將其插入到該資料流時，會呼叫 **str**. [fill](../standard-library/basic-ios-class.md#fill)( `Ch`)，然後傳回 **str**。 **Elem** 類型必須與資料流 **str** 的元素類型相同。  
  
### <a name="example"></a>範例  
  如需使用 `setfill` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。  
  
##  <a name="setiosflags"></a>  setiosflags  
 設定指定的旗標。  
  
```  
T2 setiosflags(ios_base::fmtflags Mask);
```  
  
### <a name="parameters"></a>參數  
 `Mask`  
 要設定的旗標。  
  
### <a name="return-value"></a>傳回值  
 操作工具會傳回一個物件，從資料流 **str** 中擷取此物件或將其插入到該資料流時，會呼叫 **str**. [setf](../standard-library/ios-base-class.md#setf)(_ *Mask*)，然後傳回 **str**。  
  
### <a name="example"></a>範例  
  如需使用 `setiosflags` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。  
  
##  <a name="setprecision"></a>  setprecision  
 設定浮點值的有效位數。  
  
```  
T5 setprecision(streamsize Prec);
```  
  
### <a name="parameters"></a>參數  
 `Prec`  
 浮點數值的有效位數。  
  
### <a name="return-value"></a>傳回值  
 操作工具會傳回一個物件，從資料流 **str** 中擷取此物件或將其插入到該資料流時，會呼叫 **str**. [precision](../standard-library/ios-base-class.md#precision)( `Prec`)，然後傳回 **str**。  
  
### <a name="example"></a>範例  
  如需使用 `setprecision` 的範例，請參閱 [setw](../standard-library/iomanip-functions.md#setw)。  
  
##  <a name="setw"></a>  setw  
 指定資料流中下一個元素的顯示欄位寬度。  
  
```  
T6 setw(streamsize Wide);
```  
  
### <a name="parameters"></a>參數  
 `Wide`  
 顯示欄位的寬度。  
  
### <a name="return-value"></a>傳回值  
 操作工具會傳回一個物件，從資料流 **str** 中擷取此物件或將其插入到該資料流時，會呼叫 **str**. [width](../standard-library/ios-base-class.md#width)(_ *Wide*)，然後傳回 **str**。  
  
### <a name="remarks"></a>備註  
 setw 只會設定資料流中下一個元素的寬度，而且必須插入在您想要為其指定寬度的每個元素前面。  
  
### <a name="example"></a>範例  
  
```cpp  
// iomanip_setw.cpp   
// compile with: /EHsc  
// Defines the entry point for the console application.  
//  
// Sample use of the following manipulators:  
//   resetiosflags  
//   setiosflags  
//   setbase  
//   setfill  
//   setprecision  
//   setw  
  
#include <iostream>  
#include <iomanip>  
  
using namespace std;  
  
const double   d1 = 1.23456789;  
const double   d2 = 12.3456789;  
const double   d3 = 123.456789;  
const double   d4 = 1234.56789;  
const double   d5 = 12345.6789;  
const long      l1 = 16;  
const long      l2 = 256;  
const long      l3 = 1024;  
const long      l4 = 4096;  
const long      l5 = 65536;  
int         base = 10;  
  
void DisplayDefault( )  
{  
   cout << endl << "default display" << endl;  
   cout << "d1 = " << d1 << endl;  
   cout << "d2 = " << d2 << endl;  
   cout << "d3 = " << d3 << endl;  
   cout << "d4 = " << d4 << endl;  
   cout << "d5 = " << d5 << endl;  
}  
  
void DisplayWidth( int n )  
{  
   cout << endl << "fixed width display set to " << n << ".\n";  
   cout << "d1 = " << setw(n) << d1 << endl;  
   cout << "d2 = " << setw(n) << d2 << endl;  
   cout << "d3 = " << setw(n) << d3 << endl;  
   cout << "d4 = " << setw(n) << d4 << endl;  
   cout << "d5 = " << setw(n) << d5 << endl;  
}  
  
void DisplayLongs( )  
{  
   cout << setbase(10);  
   cout << endl << "setbase(" << base << ")" << endl;  
   cout << setbase(base);  
   cout << "l1 = " << l1 << endl;  
   cout << "l2 = " << l2 << endl;  
   cout << "l3 = " << l3 << endl;  
   cout << "l4 = " << l4 << endl;  
   cout << "l5 = " << l5 << endl;  
}  
  
int main( int argc, char* argv[] )  
{  
   DisplayDefault( );  
  
   cout << endl << "setprecision(" << 3 << ")" << setprecision(3);  
   DisplayDefault( );  
  
   cout << endl << "setprecision(" << 12 << ")" << setprecision(12);  
   DisplayDefault( );  
  
   cout << setiosflags(ios_base::scientific);  
   cout << endl << "setiosflags(" << ios_base::scientific << ")";  
   DisplayDefault( );  
  
   cout << resetiosflags(ios_base::scientific);  
   cout << endl << "resetiosflags(" << ios_base::scientific << ")";  
   DisplayDefault( );  
  
   cout << endl << "setfill('" << 'S' << "')" << setfill('S');  
   DisplayWidth(15);  
   DisplayDefault( );  
  
   cout << endl << "setfill('" << ' ' << "')" << setfill(' ');  
   DisplayWidth(15);  
   DisplayDefault( );  
  
   cout << endl << "setprecision(" << 8 << ")" << setprecision(8);  
   DisplayWidth(10);  
   DisplayDefault( );  
  
   base = 16;  
   DisplayLongs( );  
  
   base = 8;  
   DisplayLongs( );  
  
   base = 10;  
   DisplayLongs( );  
  
   return   0;  
}  
```  
  
```Output  
  
default display  
d1 = 1.23457  
d2 = 12.3457  
d3 = 123.457  
d4 = 1234.57  
d5 = 12345.7  
  
setprecision(3)  
default display  
d1 = 1.23  
d2 = 12.3  
d3 = 123  
d4 = 1.23e+003  
d5 = 1.23e+004  
  
setprecision(12)  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setiosflags(4096)  
default display  
d1 = 1.234567890000e+000  
d2 = 1.234567890000e+001  
d3 = 1.234567890000e+002  
d4 = 1.234567890000e+003  
d5 = 1.234567890000e+004  
  
resetiosflags(4096)  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setfill('S')  
fixed width display set to 15.  
d1 = SSSSS1.23456789  
d2 = SSSSS12.3456789  
d3 = SSSSS123.456789  
d4 = SSSSS1234.56789  
d5 = SSSSS12345.6789  
  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setfill(' ')  
fixed width display set to 15.  
d1 =      1.23456789  
d2 =      12.3456789  
d3 =      123.456789  
d4 =      1234.56789  
d5 =      12345.6789  
  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setprecision(8)  
fixed width display set to 10.  
d1 =  1.2345679  
d2 =  12.345679  
d3 =  123.45679  
d4 =  1234.5679  
d5 =  12345.679  
  
default display  
d1 = 1.2345679  
d2 = 12.345679  
d3 = 123.45679  
d4 = 1234.5679  
d5 = 12345.679  
  
setbase(16)  
l1 = 10  
l2 = 100  
l3 = 400  
l4 = 1000  
l5 = 10000  
  
setbase(8)  
l1 = 20  
l2 = 400  
l3 = 2000  
l4 = 10000  
l5 = 200000  
  
setbase(10)  
l1 = 16  
l2 = 256  
l3 = 1024  
l4 = 4096  
l5 = 65536  
```  
  
## <a name="see-also"></a>另請參閱  
 [\<iomanip>](../standard-library/iomanip.md)

