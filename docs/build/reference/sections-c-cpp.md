---
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: 7b6708e760a85a137a01718d07a5f167de849220
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485861"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

導入了一個或多個區段`definitions`所存取規範，在您的專案輸出檔的區段。

```
SECTIONS
definitions
```

## <a name="remarks"></a>備註

每一個定義都必須在不同的行上。 `SECTIONS`關鍵字可以在第一個定義的同一行上或前面的行。 .Def 檔可以包含一或多個`SECTIONS`陳述式。

這`SECTIONS`陳述式在映像檔案中，設定一或多個區段的屬性，而且可用來覆寫區段的每個類型的預設屬性。

格式`definitions`是：

`.section_name specifier`

何處`.section_name`是在程式映像中的區段名稱和`specifier`是一或多個下列存取修飾詞：

|修飾詞|描述|
|--------------|-----------------|
|`EXECUTE`|區段是可執行檔|
|`READ`|允許對於資料的讀取的作業|
|`SHARED`|共用區段載入影像的所有處理程序|
|`WRITE`|允許對於資料的寫入作業|

以空格分隔規範的名稱。 例如: 

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` 標記的區段的清單開頭`definitions`。 每個`definition`必須位於不同行上。 `SECTIONS`關鍵字可以在同一行與第一個`definition`或在前面的行上。 .Def 檔可以包含一或多個`SECTIONS`陳述式。 `SEGMENTS`的同義字支援關鍵字`SECTIONS`。

舊版的 Visual c + + 支援：

```
section [CLASS 'classname'] specifier
```

`CLASS`關鍵字是支援的相容性，但會忽略。

對等的方法，可指定區段屬性是使用[/section](../../build/reference/section-specify-section-attributes.md)選項。

## <a name="see-also"></a>另請參閱

[模組定義陳述式的規則](../../build/reference/rules-for-module-definition-statements.md)