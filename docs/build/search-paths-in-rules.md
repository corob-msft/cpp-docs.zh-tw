---
title: 在規則中搜尋路徑
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: 26b02fa76920f0d0ff380dacd5aa76cfe8e92c79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649965"
---
# <a name="search-paths-in-rules"></a>在規則中搜尋路徑

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>備註

推斷規則適用於相依性才完全相依性中指定的路徑比對的推斷規則的路徑。 指定相依項的目錄*frompath* ] 和 [目標目錄中的*topath*; 不允許使用任何空格。 指定每個延伸模組只能有一個路徑。 上一個延伸模組的路徑會需要在其他路徑。 若要指定目前的目錄，請使用句號 （.） 或空的大括號 （{}）。 巨集可代表*frompath*並*topath*; 它們會在前置處理期間叫用。

## <a name="example"></a>範例

### <a name="code"></a>程式碼

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>另請參閱

[定義規則](../build/defining-a-rule.md)