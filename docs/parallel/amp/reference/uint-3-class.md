---
title: "uint_3 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::uint_3::get_xz
- amp_short_vectors/Concurrency::graphics::uint_3::set_yzx
- amp_short_vectors/Concurrency::graphics::uint_3::get_y
- amp_short_vectors/Concurrency::graphics::uint_3::get_yzx
- amp_short_vectors/Concurrency::graphics::uint_3::get_yz
- amp_short_vectors/Concurrency::graphics::uint_3::yzx
- amp_short_vectors/Concurrency::graphics::uint_3::get_z
- amp_short_vectors/Concurrency::graphics::uint_3::z
- amp_short_vectors/Concurrency::graphics::uint_3::xy
- amp_short_vectors/Concurrency::graphics::uint_3::gr
- amp_short_vectors/Concurrency::graphics::uint_3::operator=
- amp_short_vectors/Concurrency::graphics::uint_3::x
- amp_short_vectors/Concurrency::graphics::uint_3::gbr
- amp_short_vectors/Concurrency::graphics::uint_3::set_xy
- amp_short_vectors/Concurrency::graphics::uint_3::g
- amp_short_vectors/Concurrency::graphics::uint_3::set_yz
- amp_short_vectors/Concurrency::graphics::uint_3::br
- amp_short_vectors/Concurrency::graphics::uint_3::get_xyz
- amp_short_vectors/Concurrency::graphics::uint_3::b
- amp_short_vectors/Concurrency::graphics::uint_3::get_yxz
- amp_short_vectors/Concurrency::graphics::uint_3::set_zyx
- amp_short_vectors/Concurrency::graphics::uint_3::get_x
- amp_short_vectors/Concurrency::graphics::uint_3::rgb
- amp_short_vectors/Concurrency::graphics::uint_3::set_zy
- amp_short_vectors/Concurrency::graphics::uint_3::brg
- amp_short_vectors/Concurrency::graphics::uint_3::set_xyz
- amp_short_vectors/Concurrency::graphics::uint_3::xyz
- amp_short_vectors/Concurrency::graphics::uint_3::set_zxy
- amp_short_vectors/Concurrency::graphics::uint_3
- amp_short_vectors/Concurrency::graphics::uint_3::get_xy
- amp_short_vectors/Concurrency::graphics::uint_3::set_yx
- amp_short_vectors/Concurrency::graphics::uint_3::get_zyx
- amp_short_vectors/Concurrency::graphics::uint_3::get_zxy
- amp_short_vectors/Concurrency::graphics::uint_3::set_y
- amp_short_vectors/Concurrency::graphics::uint_3::yx
- amp_short_vectors/Concurrency::graphics::uint_3::grb
- amp_short_vectors/Concurrency::graphics::uint_3::operator+=
- amp_short_vectors/Concurrency::graphics::uint_3::set_x
- amp_short_vectors/Concurrency::graphics::uint_3::operator/=
- amp_short_vectors/Concurrency::graphics::uint_3::rbg
- amp_short_vectors/Concurrency::graphics::uint_3::set_zx
- amp_short_vectors/Concurrency::graphics::uint_3::set_z
- amp_short_vectors/Concurrency::graphics::uint_3::get_zx
- amp_short_vectors/Concurrency::graphics::uint_3::bgr
- amp_short_vectors/Concurrency::graphics::uint_3::get_xzy
- amp_short_vectors/Concurrency::graphics::uint_3::get_yx
- amp_short_vectors/Concurrency::graphics::uint_3::bg
- amp_short_vectors/Concurrency::graphics::uint_3::r
- amp_short_vectors/Concurrency::graphics::uint_3::xzy
- amp_short_vectors/Concurrency::graphics::uint_3::zyx
- amp_short_vectors/Concurrency::graphics::uint_3::set_xz
- amp_short_vectors/Concurrency::graphics::uint_3::rg
- amp_short_vectors/Concurrency::graphics::uint_3::zxy
- amp_short_vectors/Concurrency::graphics::uint_3::zy
- amp_short_vectors/Concurrency::graphics::uint_3::yz
- amp_short_vectors/Concurrency::graphics::uint_3::zx
- amp_short_vectors/Concurrency::graphics::uint_3::gb
- amp_short_vectors/Concurrency::graphics::uint_3::operator--
- amp_short_vectors/Concurrency::graphics::uint_3::set_yxz
- amp_short_vectors/Concurrency::graphics::uint_3::get_zy
- amp_short_vectors/Concurrency::graphics::uint_3::operator++
- amp_short_vectors/Concurrency::graphics::uint_3::operator-
- amp_short_vectors/Concurrency::graphics::uint_3::y
- amp_short_vectors/Concurrency::graphics::uint_3::xz
- amp_short_vectors/Concurrency::graphics::uint_3::rb
- amp_short_vectors/Concurrency::graphics::uint_3::operator*=
- amp_short_vectors/Concurrency::graphics::uint_3::yxz
- amp_short_vectors/Concurrency::graphics::uint_3::set_xzy
- amp_short_vectors/Concurrency::graphics::uint_3::operator-=
dev_langs:
- C++
ms.assetid: 5e22c277-9d4f-4a3a-b38c-a83d5fcab33c
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 034478144d77abcc9dba8bf1a1909c4711f7119c
ms.contentlocale: zh-tw
ms.lasthandoff: 03/17/2017

---
# <a name="uint3-class"></a>uint_3 類別
表示短向量的三個不帶正負號的整數。  
  
## <a name="syntax"></a>語法  
  
```  
class uint_3;  
```  
  
## <a name="members"></a>Members  
  
### <a name="public-typedefs"></a>公用 Typedefs  
  
|名稱|描述|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[uint_3 建構函式](#ctor)|多載。 預設建構函式，初始化為 0 的所有項目。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|uint_3::get_x||  
|uint_3::get_xy||  
|uint_3::get_xyz||  
|uint_3::get_xz||  
|uint_3::get_xzy||  
|uint_3::get_y||  
|uint_3::get_yx||  
|uint_3::get_yxz||  
|uint_3::get_yz||  
|uint_3::get_yzx||  
|uint_3::get_z||  
|uint_3::get_zx||  
|uint_3::get_zxy||  
|uint_3::get_zy||  
|uint_3::get_zyx||  
|uint_t::ref_b||  
|uint_t::ref_g||  
|uint_t::ref_r||  
|uint_t::ref_x||  
|uint_t::ref_y||  
|uint_t::ref_z||  
|uint_3::set_x||  
|uint_3::set_xy||  
|uint_3::set_xyz||  
|uint_3::set_xz||  
|uint_3::set_xzy||  
|uint_3::set_y||  
|uint_3::set_yx||  
|uint_3::set_yxz||  
|uint_3::set_yz||  
|uint_3::set_yzx||  
|uint_3::set_z||  
|uint_3::set_zx||  
|uint_3::set_zxy||  
|uint_3::set_zy||  
|uint_3::set_zyx||  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|說明|  
|----------|-----------------|  
|uint_3::operator-||  
|uint_3::operator %=||  
|uint_3::operator = i||  
|uint_3::operator * =||  
|uint_3::operator / =||  
|uint_3::operator ^ =||  
|uint_3::operator | =||  
|uint_3::operator ~||  
|uint_3::operator + +||  
|uint_3::operator + =||  
|uint_3::operator\<=||  
|uint_3::operator =||  
|uint_3::operator =||  
|uint_3::operator >> =||  
  
### <a name="public-constants"></a>公用常數  
  
|名稱|描述|  
|----------|-----------------|  
|[大小常數](#uint_3__size)||  
  
### <a name="public-data-members"></a>公用資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|uint_3::b||  
|uint_3::bg||  
|uint_3::bgr||  
|uint_3::br||  
|uint_3::brg||  
|uint_3::g||  
|uint_3::gb||  
|uint_3::gbr||  
|uint_3::gr||  
|uint_3::grb||  
|uint_3::r||  
|uint_3::rb||  
|uint_3::rbg||  
|uint_3::rg||  
|uint_3::rgb||  
|uint_3::x||  
|uint_3::xy||  
|uint_3::xyz||  
|uint_3::xz||  
|uint_3::xzy||  
|uint_3::y||  
|uint_3::yx||  
|uint_3::yxz||  
|uint_3::yz||  
|uint_3::yzx||  
|uint_3::z||  
|uint_3::zx||  
|uint_3::zxy||  
|uint_3::zy||  
|uint_3::zyx||  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `uint_3`  
  
## <a name="requirements"></a>需求  
 **標頭︰** amp_short_vectors.h  
  
 **命名空間︰** concurrency:: graphics  
  
##  <a name="ctor"></a>uint_3 

 預設建構函式，初始化為 0 的所有項目。  
  
```  
uint_3() restrict(amp,
    cpu);

 
uint_3(
    unsigned int _V0,  
    unsigned int _V1,  
    unsigned int _V2) restrict(amp,
    cpu);

 
uint_3(
    unsigned int _V) restrict(amp,
    cpu);

 
uint_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline uint_3(
    const double_3& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>參數  
 `_V0`  
 要初始化項目 0 的值。  
  
 `_V1`  
 要初始化項目 1 的值。  
  
 `_V2`  
 要初始化項目 2 的值。  
  
 `_V`  
 初始設定的值。  
  
 `_Other`  
 用來初始化物件。  
  
##  <a name="uint_3__size"></a>大小 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>另請參閱  
 [Concurrency::graphics 命名空間](concurrency-graphics-namespace.md)
