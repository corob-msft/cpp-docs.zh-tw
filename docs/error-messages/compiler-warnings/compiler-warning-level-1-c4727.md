---
title: 編譯器警告 (層級 1) C4727
ms.date: 11/04/2016
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: be1a248fc2709706e137b543344966735c19064e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490567"
---
# <a name="compiler-warning-level-1-c4727"></a>編譯器警告 (層級 1) C4727

「 PCH 具名 pch_file obj_file_1 和 obj_file_2 中找到的相同時間戳記。  使用第一個 PCH。

編譯與多個編譯單位時，就會發生 C4727 **/Yc**，而且編譯器能夠將所有的.obj 檔案，具有相同的.pch 時間戳記。

若要解決，編譯一個來源檔案，並 **/Yc /c** （建立 pch） 時，與其他人使用分開編譯 **/Yu /c** （使用 pch），然後將它們連結在一起。

因此，如果您執行下列動作，會產生 C4727︰

**cl /clr /GL a.cpp b.cpp c.cpp /Ycstdafx.h**

您必須執行下列改為：

**cl /clr /GL a.cpp /Ycstdafx.h /c**

**cl /clr /GL b.cpp c.cpp /Yustdafx.h /link a.obj**

如需詳細資訊，請參閱

- [/Yc (建立先行編譯標頭檔)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (使用先行編譯標頭檔)](../../build/reference/yu-use-precompiled-header-file.md)