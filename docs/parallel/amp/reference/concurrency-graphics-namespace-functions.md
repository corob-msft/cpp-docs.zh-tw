---
title: "Concurrency:: graphics 命名空間函式 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::fast_math::copy_async
- amp_graphics/Concurrency::fast_math::copy
dev_langs:
- C++
ms.assetid: ace01cd5-29d3-4356-930e-c81a61c5f934
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a9def518f951e6fbae788b69893cc7205053b411
ms.lasthandoff: 03/17/2017

---
# <a name="concurrencygraphics-namespace-functions"></a>Concurrency:: graphics 命名空間函式
|||  
|-|-|  
|[copy](#copy)|[copy_async](#copy_async)|  
  
##  <a name="copy"></a>copy 函式 （concurrency:: graphics 命名空間）  
 將來源紋理複製到目的地緩衝區中，或將來源緩衝區複製到目的緩衝區。 此函式的一般形式是`copy(src, dest)`。  
  
```  
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type>  
>  
void copy (
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(
    const void* _Src,  
    unsigned int _Src_byte_size,  
    _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>void copy(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy(
    const _Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
void copy (
    const _Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture,  
    void>::type 
>  
void copy (
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>參數  
 `_Copy_extent`  
 複製紋理區段的範圍。  
  
 `_Dst`  
 要複製到的物件。  
  
 `_Dst_byte_size`  
 目的地中的位元組數目。  
  
 `_Dst_type`  
 目的地物件的型別。  
  
 `_Dst_offset`  
 中要開始複製目的地的位移。  
  
 `InputIterator`  
 輸入 interator 型別。  
  
 `OutputIterator`  
 輸出迭代器類型。  
  
 `_Src`  
 若要複製的物件。  
  
 `_Src_byte_size`  
 在來源中的位元組數目。  
  
 `_Src_type`  
 來源物件的型別。  
  
 `_Src_offset`  
 要從中開始複製的來源中的位移。  
  
 `first`  
 在來源容器的開頭迭代器。  
  
 `last`  
 結束迭代器，為來源容器。  
  
##  <a name="copy_async"></a>copy_async 函式 （concurrency:: graphics 命名空間）  
 以非同步方式將來源紋理複製到目的地緩衝區中，或將來源緩衝區複製到目的地緩衝區，然後傳回[completion_future](completion-future-class.md)可以等候的物件。 加速器上執行的程式碼時，無法複製資料。 此函式的一般形式是`copy(src, dest)`。  
  
```  
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template<
    typename _Src_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const _Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    _Out_ void* _Dst,  
    unsigned int _Dst_byte_size);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst);

 
template <
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(
    const void* _Src,  
    unsigned int _Src_byte_size, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst);

 
template <
    typename InputIterator,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(InputIterator first, InputIterator last, _Dst_type& _Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Dst_type::rank>& _Copy_extent);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename OutputIterator,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& !details::texture_traits<OutputIterator>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset,  
    const extent<_Src_type::rank>& _Copy_extent,  
    OutputIterator _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src, _Dst_type& _Dst);

 
template <
    typename _Src_type,  
    typename _Dst_type,  
    typename = typename std::enable_if<details::texture_traits<_Src_type>::is_texture&& details::texture_traits<_Dst_type>::is_texture, void>::type  
>  
concurrency::completion_future copy_async(_Src_type& _Src,  
    const index<_Src_type::rank>& _Src_offset, _Dst_type &_Dst,  
    const index<_Dst_type::rank>& _Dst_offset,  
    const extent<_Src_type::rank>& _Copy_extent);
```  
  
### <a name="parameters"></a>參數  
 `_Copy_extent`  
 複製紋理區段的範圍。  
  
 `_Dst`  
 要複製到的物件。  
  
 `_Dst_byte_size`  
 目的地中的位元組數目。  
  
 `_Dst_type`  
 目的地物件的型別。  
  
 `_Dst_offset`  
 中要開始複製目的地的位移。  
  
 `InputIterator`  
 輸入 interator 型別。  
  
 `OutputIterator`  
 輸出迭代器類型。  
  
 `_Src`  
 若要複製的物件。  
  
 `_Src_byte_size`  
 在來源中的位元組數目。  
  
 `_Src_type`  
 來源物件的型別。  
  
 `_Src_offset`  
 要從中開始複製的來源中的位移。  
  
 `first`  
 在來源容器的開頭迭代器。  
  
 `last`  
 結束迭代器，為來源容器。  

## <a name="requirements"></a>需求  
 **標頭︰** amp_graphics.h  
  
 **命名空間︰** concurrency:: graphics 

## <a name="see-also"></a>另請參閱  
 [Concurrency::graphics 命名空間](concurrency-graphics-namespace.md)
