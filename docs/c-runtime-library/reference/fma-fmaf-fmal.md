---
title: fma、fmaf、fmal
ms.date: 04/05/2018
apiname:
- fma
- fmaf
- fmal
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fma
- fmaf
- fmal
- math/fma
- math/fmaf
- math/fmal
helpviewer_keywords:
- fma function
- fmaf function
- fmal function
ms.assetid: 584a6037-da1e-4e86-9f0c-97aae86de0c0
ms.openlocfilehash: f96592e245e443bae2f3334da51cae5572753708
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517796"
---
# <a name="fma-fmaf-fmal"></a>fma、fmaf、fmal

將兩個值相乘，並加上第三個值，然後對結果進行四捨五入，而且不會因中值四捨五入而遺失任何精確度。

## <a name="syntax"></a>語法

```C
double fma(
   double x,
   double y,
   double z
);

float fma(
   float  x,
   float  y,
   float z
); //C++ only

long double fma(
   long double  x,
   long double  y,
   long double z
); //C++ only

float fmaf(
   float  x,
   float  y,
   float z
);

long double fmal(
   long double  x,
   long double  y,
   long double z
);
```

### <a name="parameters"></a>參數

*x*<br/>
要相乘的第一個值。

*y*<br/>
要相乘的第二個值。

*z*<br/>
要加入的值。

## <a name="return-value"></a>傳回值

傳回 `(x * y) + z`。 傳回值接著會使用目前的四捨五入格式來進行四捨五入。

否則，可能會傳回下列其中一個值：

|問題|Return|
|-----------|------------|
|*x* = 無限大*y* = 0 或<br /><br /> *x* = 0 時， *y* = INFINITY|NaN|
|*x*或是*y* = 確切常见無限大*z*正負號相反 = INFINITY|NaN|
|*x*或是*y* = NaN|NaN|
|不 (*x* = 0， *y*= 無限制) 和*z* = NaN<br /><br /> 不 (*x*= 無限制， *y*= 0) 和*z* = NaN|NaN|
|溢位範圍錯誤|±HUGE_VAL、 ±HUGE_VALF 或 ±HUGE_VALL|
|反向溢位範圍錯誤|四捨五入後的正確值。|

依 [_matherr](matherr.md) 中的指定回報錯誤。

## <a name="remarks"></a>備註

因為 c + + 允許多載，您可以呼叫多載**fma**採用並傳回**float**並**長** **double**類型。 在 C 程式中， **fma**一律採用並傳回**double**。

此函式會計算值，就像它採用無限精確度，然後將最終結果進行四捨五入。

## <a name="requirements"></a>需求

|功能|C 標頭|C++ 標頭|
|--------------|--------------|------------------|
|**fma**， **fmaf**， **fmal**|\<math.h>|\<cmath>|

如需其他相容性資訊，請參閱 [相容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>另請參閱

[依字母順序排列的函式參考](crt-alphabetical-function-reference.md)<br/>
[remainder、remainderf、remainderl](remainder-remainderf-remainderl.md)<br/>
[remquo、remquof、remquol](remquo-remquof-remquol.md)<br/>
