---
title: "CGlobalHeap 類別 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGlobalHeap
- ATLMEM/ATL::CGlobalHeap
- ATLMEM/ATL::CGlobalHeap::Allocate
- ATLMEM/ATL::CGlobalHeap::Free
- ATLMEM/ATL::CGlobalHeap::GetSize
- ATLMEM/ATL::CGlobalHeap::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CGlobalHeap class
ms.assetid: e348d838-3aa7-4bee-a1b3-cd000c99f834
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: f8b4276202a507e2afeb05d10a37fa16565870e8
ms.contentlocale: zh-tw
ms.lasthandoff: 02/24/2017

---
# <a name="cglobalheap-class"></a>CGlobalHeap 類別
這個類別會實作[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 全域堆積函式的使用。  
  
> [!IMPORTANT]
>  這個類別及其成員不能在 Windows 執行階段中執行的應用程式。  
  
## <a name="syntax"></a>語法  
  
```
class CGlobalHeap : public IAtlMemMgr
```  
  
## <a name="members"></a>Members  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[CGlobalHeap::Allocate](#allocate)|呼叫這個方法來配置記憶體區塊。|  
|[CGlobalHeap::Free](#free)|呼叫此方法以釋放此記憶體管理員所配置的記憶體區塊。|  
|[CGlobalHeap::GetSize](#getsize)|呼叫這個方法，以取得此記憶體管理員所配置的記憶體區塊配置的大小。|  
|[CGlobalHeap::Reallocate](#reallocate)|呼叫這個方法來重新配置此記憶體管理員所配置的記憶體。|  
  
## <a name="remarks"></a>備註  
 `CGlobalHeap`實作使用 Win32 全域堆積函式的記憶體配置函式。  
  
> [!NOTE]
>  全域堆積函式會低於其他記憶體管理函式，但並未提供最多的功能。 因此，新的應用程式應該使用[堆積函式](http://msdn.microsoft.com/library/windows/desktop/aa366711)。 這些是用於[CWin32Heap](../../atl/reference/cwin32heap-class.md)類別。 全域函式仍會使用 DDE 和剪貼簿函式。  
  
## <a name="example"></a>範例  
 請參閱範例[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `IAtlMemMgr`  
  
 `CGlobalHeap`  
  
## <a name="requirements"></a>需求  
 **標頭︰** atlmem.h  
  
##  <a name="allocate"></a>CGlobalHeap::Allocate  
 呼叫這個方法來配置記憶體區塊。  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>參數  
 `nBytes`  
 在新記憶體區塊中要求的位元組數目。  
  
### <a name="return-value"></a>傳回值  
 傳回新配置記憶體區塊開頭的指標。  
  
### <a name="remarks"></a>備註  
 呼叫[CGlobalHeap::Free](#free)或[CGlobalHeap::Reallocate](#reallocate)釋放透過這個方法配置的記憶體。  
  
 使用實作[GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)旗標參數與**GMEM_FIXED**。  
  
##  <a name="free"></a>CGlobalHeap::Free  
 呼叫此方法以釋放此記憶體管理員所配置的記憶體區塊。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>參數  
 `p`  
 此記憶體管理員先前所配置之記憶體的指標。 NULL 是有效的值，並不執行任何動作。  
  
### <a name="remarks"></a>備註  
 使用實作[GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)。  
  
##  <a name="getsize"></a>CGlobalHeap::GetSize  
 呼叫這個方法，以取得此記憶體管理員所配置的記憶體區塊配置的大小。  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>參數  
 `p`  
 此記憶體管理員先前所配置之記憶體的指標。  
  
### <a name="return-value"></a>傳回值  
 傳回配置的記憶體區塊大小，以位元組為單位。  
  
### <a name="remarks"></a>備註  
 使用實作[GlobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593)。  
  
##  <a name="reallocate"></a>CGlobalHeap::Reallocate  
 呼叫這個方法來重新配置此記憶體管理員所配置的記憶體。  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>參數  
 `p`  
 此記憶體管理員先前所配置之記憶體的指標。  
  
 `nBytes`  
 在新記憶體區塊中要求的位元組數目。  
  
### <a name="return-value"></a>傳回值  
 傳回新配置記憶體區塊開頭的指標。  
  
### <a name="remarks"></a>備註  
 呼叫[CGlobalHeap::Free](#free)釋放透過這個方法配置的記憶體。  
  
 使用實作[GlobalReAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)。  
  
## <a name="see-also"></a>另請參閱  
 [類別概觀](../../atl/atl-class-overview.md)   
 [CComHeap 類別](../../atl/reference/ccomheap-class.md)   
 [CWin32Heap 類別](../../atl/reference/cwin32heap-class.md)   
 [CLocalHeap 類別](../../atl/reference/clocalheap-class.md)   
 [CCRTHeap 類別](../../atl/reference/ccrtheap-class.md)   
 [IAtlMemMgr 類別](../../atl/reference/iatlmemmgr-class.md)
