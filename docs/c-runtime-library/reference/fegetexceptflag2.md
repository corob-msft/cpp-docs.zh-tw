---
title: fegetexceptflag
ms.date: 04/05/2018
apiname:
- fegetexceptflag
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fegetexceptflag
- fenv/fegetexceptflag
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
ms.openlocfilehash: 43259001bd05bb7df9e2e1636c174018dcdaef3c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "51522645"
---
# <a name="fegetexceptflag"></a>fegetexceptflag

儲存目前的指定浮點例外狀況旗標的狀態。

## <a name="syntax"></a>語法

```C
int fegetexceptflag(
   fexcept_t* pstatus,
   int excepts
);
```

### <a name="parameters"></a>參數

*pstatus*<br/>
指標**fexcept_t**物件，包含目前的值，指定例外狀況旗標*removed*。

*removed*<br/>
在中儲存的浮點例外狀況旗標*pstatus*。

## <a name="return-value"></a>傳回值

成功時會傳回 0。 否則，傳回非零值。

## <a name="remarks"></a>備註

**Fegetexceptflag**函式會儲存所指定的浮點例外狀況狀態旗標的目前狀態*removed*中**fexcept_t**指向的物件*pstatus*。  *pstatus*必須指向有效**fexcept_t**物件或後續行為是未定義。 **Fegetexceptflag**函式支援這些例外狀況巨集，定義於\<fenv.h >:

|例外狀況巨集|描述|
|---------------------|-----------------|
|FE_DIVBYZERO|在稍早的浮點運算中發生的獨一性或極錯誤，已建立無限大值。|
|FE_INEXACT|函式已強制四捨五入稍早的浮點運算預存結果。|
|FE_INVALID|在稍早的浮點運算中發生的網域錯誤。|
|FE_OVERFLOW|發生範圍錯誤，稍早的浮點運算結果太大，無法表示。|
|FE_UNDERFLOW|稍早的浮點運算結果太小，無法以完整精確度表示；已建立 denormal 值。|
|FE_ALLEXCEPT|所有受支援浮點例外狀況的位元 OR。|

*Removed*引數可以是零，其中一個支援的浮點例外狀況巨集，或位元，或是兩個或以上巨集。 未定義任何其他引數值的效果。

若要使用此函式，您必須在呼叫之前使用 `#pragma fenv_access(on)` 指示詞，以關閉可能會妨礙存取的浮點最佳化作業。 如需詳細資訊，請參閱 [fenv_access](../../preprocessor/fenv-access.md)。

## <a name="requirements"></a>需求

|功能|C 標頭|C++ 標頭|
|--------------|--------------|------------------|
|**fegetexceptflag**|\<fenv.h>|\<cfenv>|

如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[依字母順序排列的函式參考](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
