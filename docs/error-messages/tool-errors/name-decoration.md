---
title: 名稱裝飾
ms.date: 09/05/2018
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: c01e684be62dbb8716f8556680b1c692af1efc45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598857"
---
# <a name="name-decoration"></a>名稱裝飾

名稱裝飾通常指的是 C++ 命名慣例，但也可以套用到一些 C 的案例。 根據預設，C++ 會使用函式名稱、參數和傳回類型來建立函式的連結器名稱。 請考慮下列函式：

```
void CALLTYPE test(void)
```

下表顯示各種呼叫慣例的連結器名稱。

|呼叫慣例|extern "C" 或 .c 檔|.cpp、.cxx 或 /TP|
|------------------------|---------------------------|------------------------|
|C 命名慣例 (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Fastcall 命名慣例 (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|標準呼叫命名慣例 (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vectorcall 命名慣例 (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

使用 extern "C" 從 C++ 呼叫 C 函式。 Extern "C" 會針對非類別的 C++ 函式強制使用 C 命名慣例。 注意編譯器參數 **/Tc**或是 **/Tp**，這會告訴編譯器忽略副檔名，並分別將檔案編譯為 C 或 c + +。 這些選項可能會導致非預期的名稱。

參數不相符的函式原型也可能導致這個錯誤。 名稱裝飾會將函式的參數納入最終的裝飾函式名稱。 使用與函式宣告中的參數類型不符合的參數類型來呼叫函式，也可能造成 LNK2001。

編譯器廠商，甚至是不同的編譯器版本之間，目前都還沒有 C++ 命名的標準。 因此，連結以其他編譯器編譯的物件檔，可能不會產生相同的命名配置，因而導致無法解析的外部符號。

## <a name="see-also"></a>另請參閱

[連結器工具錯誤 LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)