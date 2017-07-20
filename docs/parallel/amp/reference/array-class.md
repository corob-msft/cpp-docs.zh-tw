---
title: "array 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- array
- AMP/array
- AMP/Concurrency::array::array
- AMP/Concurrency::array::copy_to
- AMP/Concurrency::array::data
- AMP/Concurrency::array::get_accelerator_view
- AMP/Concurrency::array::get_associated_accelerator_view
- AMP/Concurrency::array::get_cpu_access_type
- AMP/Concurrency::array::get_extent
- AMP/Concurrency::array::reinterpret_as
- AMP/Concurrency::array::section
- AMP/Concurrency::array::view_as
- AMP/Concurrency::array::rank
- AMP/Concurrency::array::accelerator_view
- AMP/Concurrency::array::associated_accelerator_view
- AMP/Concurrency::array::cpu_access_type
- AMP/Concurrency::array::extent
dev_langs:
- C++
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
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
ms.openlocfilehash: 470918d62357a8dd463db35b4d929e7ec5c2f251
ms.contentlocale: zh-tw
ms.lasthandoff: 03/17/2017

---
# <a name="array-class"></a>array 類別
表示用來將資料移至對應的資料容器。  
  
## <a name="syntax"></a>語法  
  
```  
template <typename value_type, int _Rank>  
friend class array;  
```  
  
#### <a name="parameters"></a>參數  
 `value_type`  
 項目類型的資料。  
  
 `_Rank`  
 陣列的陣序規範。  
  
## <a name="members"></a>Members  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|描述|  
|----------|-----------------|  
|[陣列建構函式](#ctor)|初始化 `array` 類別的新執行個體。|  
|[~ array 解構函式](#dtor)|終結`array`物件。|  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[copy_to](#copy_to)|將陣列的內容複製到另一個陣列。|  
|[data](#data)|傳回陣列的未經處理資料的指標。|  
|[get_accelerator_view](#get_accelerator_view)|傳回[accelerator_view](accelerator-view-class.md)物件，代表陣列的配置位置。 這個屬性可以只在 CPU 上存取。|  
|[get_associated_accelerator_view](#get_associated_accelerator_view)|取得第二個[accelerator_view](accelerator-view-class.md)臨時的建構函式呼叫來具現化時，做為參數傳遞的物件`array`物件。|  
|[get_cpu_access_type](#get_cpu_access_type)|傳回[access_type](concurrency-namespace-enums-amp.md#access_type)的陣列。 這個方法可以只在 CPU 上存取。|  
|[get_extent](#get_extent)|傳回[範圍](extent-class.md)物件的陣列。|  
|[reinterpret_as](#reinterpret_as)|傳回一維陣列，包含在所有項目`array`物件。|  
|[section](#section)|傳回的子區段`array`物件在指定的來源，並選擇性地，具有指定的範圍。|  
|[view_as](#view_as)|傳回[array_view](array-view-class.md)建構從物件`array`物件。|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|說明|  
|----------|-----------------|  
|[運算子 std:: vector&lt;value_type&gt;](#operator_vec)|使用`copy(*this, vector)`來隱含地將陣列轉換成 std::[向量](../../../standard-library/vector-class.md)物件。|  
|[operator （)](#operator_call)|傳回參數所指定的項目值。|  
|[operator]](#operator_at)|傳回指定索引處的項目。|  
|[operator=](#operator_eq)|將指定的內容複製`array`到這裡的物件。|  
  
### <a name="public-constants"></a>公用常數  
  
|名稱|說明|  
|----------|-----------------|  
|[rank 常數](#rank)|儲存陣列的陣序規範。|  
  
### <a name="public-data-members"></a>公用資料成員  
  
|名稱|描述|  
|----------|-----------------|  
|[accelerator_view](#accelerator_view)|取得[accelerator_view](accelerator-view-class.md)物件，代表陣列的配置位置。 這個屬性可以只在 CPU 上存取。|  
|[associated_accelerator_view](#associated_accelerator_view)|取得第二個[accelerator_view](accelerator-view-class.md)臨時的建構函式呼叫來具現化時，做為參數傳遞的物件`array`物件。|  
|[cpu_access_type](#cpu_access_type)|取得[access_type](concurrency-namespace-enums-amp.md#access_type)表示 CPU 存取陣列的儲存體的方式。|  
|[extent](#extent)|取得定義陣列形狀的程度。|  
  
## <a name="remarks"></a>備註  
 型別`array<T,N>`代表密集及一般 （不不規則） *N*-位於特定的位置，例如快速鍵或 CPU 的二維陣列。 陣列中元素的資料型別是`T`，該值必須與目標加速器相容的型別。 雖然順位、 `N`，(的陣列以靜態方式判斷類型的一部分，陣列的範圍取決於執行階段，並使用類別來表示`extent<N>`。  
  
 陣列可以有任意數目的維度，雖然有些功能專門用於`array`排名一、 兩個與三個物件。 如果您省略維度引數，預設值為 1。  
  
 陣列資料是連續配置在記憶體中。 不同的其中一個最小顯著性的維度中的項目會在記憶體中相鄰的。  
  
 陣列是以邏輯方式被視為實值型別，因為當陣列複製到另一個陣列，要執行的深層複本。 這兩個陣列永遠不會指向相同的資料。  
  
 `array<T,N>`類型用在許多案例︰  
  
-   為資料容器，可用於計算加速器。  
  
-   為資料容器，以保留在主機 CPU 記憶體 （也可用於從其他陣列複製）。  
  
-   為暫存物件做為主機對裝置複本中的快速媒介。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `array`  
  
## <a name="requirements"></a>需求  
 **標頭︰** amp.h  
  
 **命名空間：** 並行  
  
##  <a name="dtor"></a>~ 陣列 

 終結`array`物件。  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="accelerator_view"></a>accelerator_view 

 取得[accelerator_view](accelerator-view-class.md)物件，代表陣列的配置位置。 這個屬性可以只在 CPU 上存取。  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="ctor"></a>陣列 

 初始化的新執行個體[array 類別](array-class.md)。 沒有預設建構函式的`array<T,N>`。 只有在 CPU 上執行所有建構函式。 它們無法 Direct3D 目標上執行。  
  
```  
explicit array(  
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);  
  
explicit array(  
    int _E0) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first, 
    _InputIterator _Src_last) restrict(cpu);
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,    
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
explicit array(  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);  
  
array(  
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av,  
    accelerator_view _Associated_Av) restrict(cpu);  
  
array(const array& _Other) restrict(cpu);  
  
array(array&& _Other) restrict(cpu);  
```  
  
### <a name="parameters"></a>參數  
 `_Associated_Av`  
 Accelerator_view 指定慣用的目標位置的陣列。  
  
 `_Av`  
 [Accelerator_view](accelerator-view-class.md)物件，指定陣列的位置。  
  
 `_Cpu_access_type`  
 想要的[access_type](concurrency-namespace-enums-amp.md#access_type) CPU 上的陣列。 此參數的預設值是`access_type_auto`離開 CPU`access_type`至執行階段決定。 實際 CPU`access_type`陣列可以使用查詢的`get_cpu_access_type`方法。  
  
 `_Extent`  
 陣列的每個維度中的延伸區。  
  
 `_E0`  
 本章節的範圍的最重要的元件。  
  
 `_E1`  
 本章節的範圍的下一步-至-最大顯著性的元件。  
  
 `_E2`  
 本章節的範圍的最小顯著性的元件。  
  
 `_InputIterator`  
 輸入 interator 型別。  
  
 `_Src`  
 若要複製的物件。  
  
 `_Src_first`  
 在來源容器的開頭迭代器。  
  
 `_Src_last`  
 結束迭代器，為來源容器。  
  
 `_Other`  
 其他資料來源。  
  
 `_Rank`  
 區段的陣序規範。  
  
 `value_type`  
 複製的項目資料型別。  
  
##  <a name="associated_accelerator_view"></a>associated_accelerator_view 

 取得第二個[accelerator_view](accelerator-view-class.md)臨時的建構函式呼叫來具現化時，做為參數傳遞的物件`array`物件。  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="copy_to"></a>copy_to 

 複製的內容`array`到另一個`array`。  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>參數  
 `_Dest`  
 [Array_view](array-view-class.md)複製到的物件。  
  
##  <a name="cpu_access_type"></a>cpu_access_type 

 取得這個陣列所允許的 CPU access_type。  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="data"></a>資料 

 傳回的未經處理資料的指標`array`。  
  
```  
value_type* data() restrict(amp, cpu);
  
const value_type* data() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>傳回值  
 未經處理資料的陣列指標。  
  
##  <a name="extent"></a>範圍 

 取得[範圍](extent-class.md)定義的圖形物件`array`。  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="get_accelerator_view"></a>get_accelerator_view 

 傳回[accelerator_view](accelerator-view-class.md)物件代表的位置，其中`array`物件配置。 這個屬性可以只在 CPU 上存取。  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;  
```    
  
### <a name="return-value"></a>傳回值  
 `accelerator_view`物件代表的位置，其中`array`物件配置。  
  
##  <a name="get_associated_accelerator_view"></a>get_associated_accelerator_view 

 取得第二個[accelerator_view](accelerator-view-class.md)臨時的建構函式呼叫來具現化時，做為參數傳遞的物件`array`物件。  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>傳回值  
 第二個[accelerator_view](accelerator-view-class.md)物件傳遞至開發用的建構函式。  
  
##  <a name="get_cpu_access_type"></a>get_cpu_access_type 

 允許為這個陣列傳回 CPU access_type。  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>傳回值  
  
##  <a name="get_extent"></a>get_extent 

 傳回[範圍](extent-class.md)物件`array`。  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>傳回值  
 `extent`物件`array`。  
  
##  <a name="operator_vec"></a>運算子 std:: vector&lt;value_type&gt; 

 使用`copy(*this, vector)`來隱含地轉換成 std:: vector 物件的陣列。  
  
```  
operator std::vector<value_type>() const restrict(cpu);
```  
  
### <a name="parameters"></a>參數  
 `value_type`  
 將向量的元素資料型別。  
  
### <a name="return-value"></a>傳回值  
 型別的物件`vector<T>`，其中包含一份陣列中所包含的資料。  
  
##  <a name="operator_call"></a>operator （) 

 傳回參數所指定的項目值。  
  
```  
value_type& operator() (const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator() (const index<_Rank>& _Index) cons  t restrict(amp,cpu);
  
value_type& operator() (int _I0, int _I1) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1) const restrict(amp,cpu)  ;
  
value_type& operator() (int _I0, int _I1, int _I2) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1, int _I2) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator()(int _I) restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator()(int _I) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>參數  
 `_Index`  
 項目的位置。  
  
 `_I0`  
 本章節的原始來源的最重要的元件。  
  
 `_I1`  
 本章節的原始來源的下一步-至-最大顯著性的元件。  
  
 `_I2`  
 本章節的原始來源的最小顯著性的元件。  
  
 `_I`  
 項目的位置。  
  
### <a name="return-value"></a>傳回值  
 參數所指定的項目值。  
  
##  <a name="operator_at"></a>operator] 

 傳回指定索引處的項目。  
  
```  
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator[]  
    (const index<_Rank>& _Index) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```  
    
### <a name="parameters"></a>參數  
 `_Index`  
 索引。  
  
 `_I`  
 索引。  
  
### <a name="return-value"></a>傳回值  
 所指定索引處的項目。  
  
##  <a name="operator_eq"></a>運算子 = 

 將指定的內容複製`array`物件。  
  
```  
array& operator= (const array& _Other) restrict(cpu);  
   
array& operator= (array&& _Other) restrict(cpu);  
 
array& operator= (  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```  
  
### <a name="parameters"></a>參數  
 `_Other`  
 `array`從複製的物件。  
  
 `_Src`  
 `array`從複製的物件。  
  
### <a name="return-value"></a>傳回值  
 參考`array`物件。  
  
##  <a name="rank"></a>陣序規範 

 儲存的陣序規範`array`。  
  
```  
static const int rank = _Rank;  
```  
## <a name="reinterpret_as"></a>reinterpret_as 

轉換到一維的 array_view，或者可能會有不同的值類型與來源陣列的陣列。

### <a name="syntax"></a>語法
``` 
template <typename _Value_type2>  
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);  
  
template <typename _Value_type2>  
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);  
``` 
  
### <a name="parameters"></a>參數  
`_Value_type2`傳回資料的資料型別。

### <a name="return-value"></a>傳回值
Array_view 或 const array_view 物件根據以 ElementType 和從 N 減少到 1 的陣序規範解譯自 T 的項目類型的陣列。

### <a name="remarks"></a>備註
有時候很容易檢視多維陣列，它是線性的一維陣列，可能是不同的值型別比來源陣列。 您可以使用這個方法來達到此目的。
**注意︰**型別重新解譯使用不同的值類型的陣列物件，而是可能不安全的作業。 我們建議您小心使用此功能。 

下列程式碼提供一個範例。

```cpp  
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...; 
array_view<float,1> v = a.reinterpret_as<float>(); 

assert(v.extent == 3*a.extent);
```  
  
##  <a name="section"></a>區段 

 傳回的子區段`array`物件在指定的來源，並選擇性地，具有指定的範圍。  
  
```  
array_view<value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const index<_Rank>& _Idx) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const index<_Rank>& _Idx) const restrict(amp,cpu);
  
array_view<value_type,1> section(
    int _I0,  
    int _E0) restrict(amp,cpu);
  
array_view<const value_type,1> section(
    int _I0,  
    int _E0) const restrict(amp,cpu);
  
array_view<value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) restrict(amp,cpu);
  
array_view<const value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);
  
array_view<value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) restrict(amp,cpu);
  
array_view<const value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>參數  
 `_E0`  
 本章節的範圍的最重要的元件。  
  
 `_E1`  
 本章節的範圍的下一步-至-最大顯著性的元件。  
  
 `_E2`  
 本章節的範圍的最小顯著性的元件。  
  
 `_Ext`  
 [範圍](extent-class.md)物件，指定區段的範圍。 原點是 0。  
  
 `_Idx`  
 [索引](index-class.md)物件，指定的來源位置。 子區段是範圍的其餘部分。  
  
 `_I0`  
 本章節的原始來源的最重要的元件。  
  
 `_I1`  
 本章節的原始來源的下一步-至-最大顯著性的元件。  
  
 `_I2`  
 本章節的原始來源的最小顯著性的元件。  
  
 `_Rank`  
 區段的陣序規範。  
  
 `_Section_extent`  
 [範圍](extent-class.md)物件，指定區段的範圍。  
  
 `_Section_origin`  
 [索引](index-class.md)物件，指定的來源位置。  
  
 `value_type`  
 複製的項目資料型別。  
  
### <a name="return-value"></a>傳回值  
 傳回的子區段`array`物件在指定的來源，並選擇性地，具有指定的範圍。 只有當`index`指定的物件，子區段包含具有索引是大於索引中的項目相關聯的方格中所有項目`index`物件。  
  
##  <a name="view_as"></a>view_as 

 轉換為這個陣列[array_view](array-view-class.md)的不同次序。  
  
```  
template <int _New_rank>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

 
template <int _New_rank>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>參數  
 `_New_rank`  
 陣序規範`extent`做為參數傳遞的物件。  
  
 `_View_extent`  
 用來建構新的範圍內[array_view](array-view-class.md)物件。  
  
 `value_type`  
 在這兩個原始項目的資料型別`array`物件並傳回`array_view`物件。  
  
### <a name="return-value"></a>傳回值  
 [Array_view](array-view-class.md)建構物件。  
  
## <a name="see-also"></a>另請參閱  
 [Concurrency 命名空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
