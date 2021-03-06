---
title: fopen_s、_wfopen_s
ms.date: 11/04/2016
apiname:
- _wfopen_s
- fopen_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fopen_s
- _tfopen_s
- _wfopen_s
helpviewer_keywords:
- _wfopen_s function
- opening files, for file I/O
- _tfopen_s function
- tfopen_s function
- wfopen_s function
- fopen_s function
- Unicode [C++], creating files
- Unicode [C++], writing files
- files [C++], opening
- Unicode [C++], files
ms.assetid: c534857e-39ee-4a3f-bd26-dfe551ac96c3
ms.openlocfilehash: 1309f991b8251bde7d614aa274d8d2e9da7a8ed3
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2018
ms.locfileid: "51333342"
---
# <a name="fopens-wfopens"></a>fopen_s、_wfopen_s

開啟檔案。 這些版本的 [fopen、_wfopen](fopen-wfopen.md) 具有 [CRT 中的安全性功能](../../c-runtime-library/security-features-in-the-crt.md)中所述的安全性增強功能。

## <a name="syntax"></a>語法

```C
errno_t fopen_s(
   FILE** pFile,
   const char *filename,
   const char *mode
);
errno_t _wfopen_s(
   FILE** pFile,
   const wchar_t *filename,
   const wchar_t *mode
);
```

### <a name="parameters"></a>參數

*pFile*<br/>
指向檔案指標 (將接收指向已開啟檔案之指標) 的指標。

*filename*<br/>
檔案名稱。

*mode*<br/>
允許的存取類型。

## <a name="return-value"></a>傳回值

如果成功，就是零，如果失敗，則為錯誤碼。 如需這些傳回碼的詳細資訊，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

### <a name="error-conditions"></a>錯誤狀況

|*pFile*|*filename*|*mode*|傳回值|內容*pFile*|
|-------------|----------------|------------|------------------|------------------------|
|**NULL**|any|any|**EINVAL**|未變更|
|any|**NULL**|any|**EINVAL**|未變更|
|any|any|**NULL**|**EINVAL**|未變更|

## <a name="remarks"></a>備註

所開啟的檔案**fopen_s**並 **_wfopen_s**不共用。 如果您需要該檔案要是可共用，使用[_fsopen、 _wfsopen](fsopen-wfsopen.md)具有適當的共用模式常數 — 例如 **_SH_DENYNO**用於讀取/寫入共用。

**Fopen_s**函式會開啟指定的檔案*filename*。 **_wfopen_s**是寬字元版本的**fopen_s**; 的引數 **_wfopen_s**是寬字元字串。 **_wfopen_s**並**fopen_s**行為相同。

**fopen_s**接受執行; 在檔案系統為有效的路徑接受 UNC 路徑以及包含對應的網路磁碟機的路徑**fopen_s**只要系統是執行程式碼有共用的存取權，或在執行時對應網路磁碟機。 當您建構路徑**fopen_s**、 不要假設磁碟機、 路徑，或網路共用執行環境中。 您可以使用正斜線 (/) 或反斜線 (\\) 作為路徑中的目錄分隔符號。

這些函式會驗證它們的參數。 如果*pFile*， *filename*，或*模式*為 null 指標，這些函式會產生無效參數例外狀況中所述[參數驗證](../../c-runtime-library/parameter-validation.md).

請務必檢查傳回值，在對檔案執行任何進一步作業之前，查看此函式是否已成功。 如果發生錯誤，傳回的錯誤碼和全域變數**errno**設定。 如需詳細資訊，請參閱 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

## <a name="unicode-support"></a>Unicode 支援

**fopen_s**支援 Unicode 檔案資料流。 若要開啟新的或現有的 Unicode 檔案，請傳遞*ccs*旗標，指定想要的編碼來**fopen_s**:

**fopen_s (& fp、 「 newfile.txt"，"rw，ccs =**_編碼_**");**

允許的值為*編碼*會**UNICODE**， **utf-8**，以及 **-16LE**。 如果那里任何指定的值*編碼*， **fopen_s**使用 ANSI 編碼方式。

如果檔案已經存在，而且已開啟來進行讀取或附加，則位元順序標記 (BOM) (如果已在檔案中) 會決定編碼方式。 BOM 編碼方式的優先權會高於的編碼方式，由*ccs*旗標。 *Ccs*編碼時才會使用不含 BOM 不存在或檔案是否為新的檔案。

> [!NOTE]
> BOM 偵測只適用於在 Unicode 模式中開啟的檔案也就藉由傳遞*ccs*旗標。

下表摘要說明模式各種*ccs*旗標，提供給**fopen_s**和檔案中的位元順序標記。

### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>根據 ccs 旗標和 BOM 使用的編碼方式

|ccs 旗標|沒有 BOM (或新檔案)|BOM：UTF-8|BOM：UTF-16|
|----------------|----------------------------|-----------------|------------------|
|**UNICODE**|**-16LE**|**UTF-8**|**-16LE**|
|**UTF-8**|**UTF-8**|**UTF-8**|**-16LE**|
|**-16LE**|**-16LE**|**UTF-8**|**-16LE**|

開啟以供在 Unicode 模式下寫入的檔案會有 BOM 自動寫入其中。

如果*模式*是 **"，ccs =**_編碼_**"**， **fopen_s**第一次嘗試開啟檔案讀取存取和寫入權限。 如果成功，則函式會讀取 BOM 以判斷檔案的編碼方式，如果不成功，則函式會使用檔案的預設編碼方式。 在任一情況下， **fopen_s**接著重新開啟檔案的唯寫存取。 (這適用於模式，不**a +**。)

### <a name="generic-text-routine-mappings"></a>一般文字常式對應

|TCHAR.H 常式|未定義 _UNICODE 和 _MBCS|_MBCS 已定義|_UNICODE 已定義|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfopen_s**|**fopen_s**|**fopen_s**|**_wfopen_s**|

字元字串*模式*指定，如下所示要求檔案的存取種類。

|*mode*|存取|
|-|-|
| **"r"** | 開啟以讀取。 如果檔案不存在或無法找到**fopen_s**呼叫就會失敗。 |
| **"w"** | 開啟空白檔案以寫入。 如果指定的檔案已存在，其內容將被終結。 |
| **"a"** | 開啟以供在檔案結尾寫入 (附加)，並且在將新資料寫入檔案之前，不會移除檔案結尾 (EOF) 標記。 如果檔案不存在時，建立檔案。 |
| **"r+"** | 開啟以進行讀取和寫入。 檔案必須存在。 |
| **"w+"** | 開啟空白檔案以進行讀取和寫入。 如果檔案存在，其內容會遭到銷毀。 |
| **"a+"** | 開啟以進行讀取和附加。 附加作業包括在將新資料寫入檔案之前移除 EOF 標記。 寫入完成後，不會還原 EOF 標記。 如果檔案不存在時，建立檔案。 |

使用開啟的檔案時 **"a"** 或是 **"a +"** 存取類型，所有寫入作業都會在檔案結尾。 檔案指標可以使用重新定位到[fseek](fseek-fseeki64.md)或是[倒轉](rewind.md)，但是它一律移回至檔案結尾之前任何寫入作業會執行，因此無法覆寫現有的資料。

**"A"** 模式不會附加到檔案之前移除 EOF 標記。 進行附加之後，MS-DOS TYPE 命令只顯示到原始 EOF 標記為止的資料，任何附加至檔案的資料都不會出現。 **"A +"** 模式會附加到檔案之前移除 EOF 標記。 附加之後，MS-DOS TYPE 命令會顯示檔案中的所有資料。 **"A +"** 模式，才能附加至使用 CTRL + Z EOF 標記終止的資料流檔案。

當 **"r +"**， **"w +"**，或 **"a +"** 指定存取類型，允許讀取和寫入。 (表示檔案是要開啟以供「更新」之用。)不過，當您從讀取切換為寫入時，輸入作業一定會遇到 EOF 標記。 如果沒有 EOF，您就必須使用檔案定位函式的介入呼叫。 檔案定位函式**fsetpos**， [fseek](fseek-fseeki64.md)，並[倒轉](rewind.md)。 當您從寫入切換為讀取時，您必須使用其中一個的介入呼叫**fflush**或是檔案定位函式。

除了上述的值，可以將下列字元包含在*模式*來指定新行字元的轉譯模式：

|*模式*修飾詞|轉譯模式|
|-|-|
| **t** | 以文字 (已轉譯) 模式開啟。 |
| **b** | 以二進位 (未轉譯) 模式開啟；抑制涉及歸位字元和換行字元的轉譯。 |

在文字 （已轉譯） 模式中，CTRL + Z 會解譯成檔案結尾字元上輸入。 在檔案開啟供讀取/寫入與 **"a +"**， **fopen_s**會檢查是否有 CTRL + Z 結尾的檔案，並盡可能加以移除。 這是因為使用[fseek](fseek-fseeki64.md)並**ftell** CTRL + Z，結束可能會導致檔案內移動[fseek](fseek-fseeki64.md)檔案結尾附近產生不當行為。

此外，在文字模式下，歸位字元復位換行的組合會轉譯成單一換行字元，輸入時，並換行字元會轉譯為歸位字元在輸出的復位換行組合。 Unicode 資料流 I/O 函式在文字模式 (預設) 下運作時，會假設來源或目的資料流是多位元組字元的序列。 因此，Unicode 資料流輸入函式會將多位元組字元轉換為寬字元 (就像呼叫 **mbtowc** 函式一樣)。 基於相同的原因，Unicode 資料流輸出函式會將寬字元轉換為多位元組字元 (就像呼叫 **wctomb** 函式一樣)。

如果**t**或是**b**中未指定*模式*，則預設轉譯模式由全域變數[_fmode](../../c-runtime-library/fmode.md)。 如果**t**或是**b**前面加上引數，函式會失敗並傳回**NULL**。

如需在 Unicode 和多位元組資料流 I/O 中使用文字和二進位模式的詳細資訊，請參閱[文字和二進位模式檔案 I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 和[文字和二進位模式的 Unicode 資料流 I/O](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)。

|*模式*修飾詞|行為|
|-|-|
| **C** | 啟用相關聯的認可旗標*檔名*使檔案緩衝區的內容會直接寫入磁碟**fflush**或是 **_flushall**呼叫。 |
| **n** | 重設相關聯的認可旗標*filename*以 「 不認可 」。 這是預設值。 如果將程式與 COMMODE.OBJ 連結，也會覆寫全域認可旗標。 除非您明確連結程式與 COMMODE.OBJ，否則全域認可旗標的預設值為 "no-commit" (請參閱 [Link Options](../../c-runtime-library/link-options.md))。 |
| **N** | 指定子處理序不繼承檔案。 |
| **S** | 指定針對但不限於磁碟的循序存取進行快取最佳化。 |
| **R** | 指定針對但不限於磁碟的隨機存取進行快取最佳化。 |
| **T** | 指定檔案做為暫存檔。 可能的話，不將其清除至磁碟。 |
| **D** | 指定檔案做為暫存檔。 當最後一個檔案指標關閉時，將其刪除。 |
| **ccs =**_編碼_ | 指定要使用的編碼的字元集 (其中**utf-8**， **-16LE**，或**UNICODE**) 此檔案。 如果您想要使用 ANSI 編碼方式，請保持為未指定。 |

有效字元*模式*中所使用的字串**fopen_s**並[_fdopen](fdopen-wfdopen.md)對應至*oflag*引數中使用[_開啟](open-wopen.md)並[_sopen](sopen-wsopen.md)、，如下所示。

|中的字元*模式*字串|對等*oflag* _open/_sopen 值|
|-------------------------------|----------------------------------------------------|
|**a**|**_O_WRONLY** &#124; **_O_APPEND** (通常 **_O_WRONLY** &#124; **_O_CREAT** &#124;* * _O_APPEND * *)|
|**+**|**_O_RDWR** &#124; **_O_APPEND** (通常 **_O_RDWR** &#124; **_O_APPEND** &#124; **_O_CREAT** )|
|**r**|**_O_RDONLY**|
|**r +**|**_O_RDWR**|
|**w**|**_O_WRONLY** (通常 **_O_WRONLY** &#124; **_O_CREAT** &#124;* * _O_TRUNC * *)|
|**w +**|**_O_RDWR** (通常 **_O_RDWR** &#124; **_O_CREAT** &#124; **_O_TRUNC**)|
|**b**|**_O_BINARY**|
|**t**|**_O_TEXT**|
|**C**|無|
|**n**|無|
|**S**|**_O_SEQUENTIAL**|
|**R**|**_O_RANDOM**|
|**T**|**_O_SHORTLIVED**|
|**D**|**_O_TEMPORARY**|
|**ccs = UNICODE**|**_O_WTEXT**|
|**ccs = utf-8**|**_O_TEXTW、_O_UTF8**|
|**ccs =-16LE**|**_O_UTF16**|

如果您使用**rb**模式中，不需要移植程式碼，並且打算讀取大量的檔案和/或不在意網路效能、 記憶體對應 Win32 檔案也可能是一個選項。

## <a name="requirements"></a>需求

|功能|必要的標頭|
|--------------|---------------------|
|**fopen_s**|\<stdio.h>|
|**_wfopen_s**|\<stdio.h> 或 \<wchar.h>|

如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>程式庫

所有版本的 [C 執行階段程式庫](../../c-runtime-library/crt-library-features.md)。

**c**， **n**，並**t** *模式*選項都是 Microsoft 擴充功能**fopen_s**及[_fdopen](fdopen-wfdopen.md)和不應在需要 ANSI 可攜性。

## <a name="example"></a>範例

```C
// crt_fopen_s.c
// This program opens two files. It uses
// fclose to close the first file and
// _fcloseall to close all remaining files.

#include <stdio.h>

FILE *stream, *stream2;

int main( void )
{
   errno_t err;

   // Open for read (will fail if file "crt_fopen_s.c" does not exist)
   err  = fopen_s( &stream, "crt_fopen_s.c", "r" );
   if( err == 0 )
   {
      printf( "The file 'crt_fopen_s.c' was opened\n" );
   }
   else
   {
      printf( "The file 'crt_fopen_s.c' was not opened\n" );
   }

   // Open for write
   err = fopen_s( &stream2, "data2", "w+" );
   if( err == 0 )
   {
      printf( "The file 'data2' was opened\n" );
   }
   else
   {
      printf( "The file 'data2' was not opened\n" );
   }

   // Close stream if it is not NULL
   if( stream )
   {
      err = fclose( stream );
      if ( err == 0 )
      {
         printf( "The file 'crt_fopen_s.c' was closed\n" );
      }
      else
      {
         printf( "The file 'crt_fopen_s.c' was not closed\n" );
      }
   }

   // All other files are closed:
   int numclosed = _fcloseall( );
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );
}
```

```Output
The file 'crt_fopen_s.c' was opened
The file 'data2' was opened
Number of files closed by _fcloseall: 1
```

## <a name="see-also"></a>另請參閱

[資料流 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[_fdopen、wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
f[reopen、_wfreopen](freopen-wfreopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
