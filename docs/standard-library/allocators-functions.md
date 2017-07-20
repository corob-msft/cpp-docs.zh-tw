---
title: "&lt;allocators&gt; 巨集 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/std::ALLOCATOR_DECL
- allocators/std::CACHE_CHUNKLIST
- allocators/std::CACHE_FREELIST
- allocators/std::CACHE_SUBALLOC
- allocators/std::SYNC_DEFAULT
ms.assetid: 9cb5ee07-1ff9-4594-ae32-3c8c6efb511a
caps.latest.revision: 12
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: da17f9af1f14df13eb3871ef9ccf785356e02de4
ms.openlocfilehash: abc1dd29ba68540a6669f7aff1bbd3dffdab616a
ms.lasthandoff: 02/24/2017

---
# <a name="ltallocatorsgt-macros"></a>&lt;allocators&gt; 巨集
||||  
|-|-|-|  
|[ALLOCATOR_DECL](#allocator_decl)|[CACHE_CHUNKLIST](#cache_chunklist)|[CACHE_FREELIST](#cache_freelist)|  
|[CACHE_SUBALLOC](#cache_suballoc)|[SYNC_DEFAULT](#sync_default)|  
  
##  <a name="allocator_decl"></a> ALLOCATOR_DECL  
 產生配置器範本類別。  
  
```
#define ALLOCATOR_DECL(cache, sync, name) <alloc_template>
```  
  
### <a name="remarks"></a>備註  
 巨集會產生範本定義 `template <class Type> class name {.....}` 和特製化 `template <> class name<void> {.....}`，而兩者共同定義使用同步處理篩選 `sync` 的配置器範本類別以及 `cache` 類型的快取。  
  
 針對可以編譯重新繫結的編譯器，產生的範本定義看起來如下︰  
```  
struct rebind
   {    /* convert a name<Type> to a name<Other> */
   typedef name<Other> other;
   };  
 ```  
 針對無法編譯重新繫結的編譯器，產生的範本定義看起來如下︰  
  
```
template <class Type<class name
    : public stdext::allocators::allocator_base<Type,
    sync<stdext::allocators::rts_alloc<cache>>>
{
public:
    name() {}
    template <class Other>
    name(const name<Other>&) {}
    template <class Other>
    name& operator= (const name<Other>&)
    {
        return *this;
    }
};
```  
  
##  <a name="cache_chunklist"></a> CACHE_CHUNKLIST  
 產生 `stdext::allocators::cache_chunklist<sizeof(Type)>`。  
  
```
#define CACHE_CHUNKLIST <cache_class>
```  
  
### <a name="remarks"></a>備註  
  
##  <a name="cache_freelist"></a> CACHE_FREELIST  
 產生 `stdext::allocators::cache_freelist<sizeof(Type), max>`。  
  
```
#define CACHE_FREELIST(max) <cache_class>
```  
  
### <a name="remarks"></a>備註  
  
##  <a name="cache_suballoc"></a> CACHE_SUBALLOC  
 產生 `stdext::allocators::cache_suballoc<sizeof(Type)>`。  
  
```
#define CACHE_SUBALLOC <cache_class>
```  
  
### <a name="remarks"></a>備註  
  
##  <a name="sync_default"></a> SYNC_DEFAULT  
 產生同步處理篩選。  
  
```
#define SYNC_DEFAULT <sync_template>
```  
  
### <a name="remarks"></a>備註  
 如果編譯器支援編譯單一執行緒和多執行緒應用程式，則針對單一執行緒應用程式，巨集會產生 `stdext::allocators::sync_none`；在所有其他情況下，則會產生 `stdext::allocators::sync_shared`。  
  
## <a name="see-also"></a>另請參閱  
 [\<allocators>](../standard-library/allocators-header.md)




