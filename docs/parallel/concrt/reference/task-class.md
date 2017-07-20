---
title: "task 類別 （並行執行階段） |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task
- PPLTASKS/concurrency::task
- PPLTASKS/concurrency::task::task
- PPLTASKS/concurrency::task::get
- PPLTASKS/concurrency::task::is_apartment_aware
- PPLTASKS/concurrency::task::is_done
- PPLTASKS/concurrency::task::scheduler
- PPLTASKS/concurrency::task::then
- PPLTASKS/concurrency::task::wait
dev_langs:
- C++
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
caps.latest.revision: 12
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
ms.openlocfilehash: e6c568b0b6a5f07df51980e1e440f31482f45846
ms.contentlocale: zh-tw
ms.lasthandoff: 03/17/2017

---
# <a name="task-class-concurrency-runtime"></a>task 類別 (並行執行階段)
平行模式程式庫 (PPL) `task` 類別。 `task` 物件代表可以非同步執行，並可與其他工作以及並行執行階段中平行演算法所產生的平行工作同時執行的工作。 成功完成時，會產生 `_ResultType` 類型的結果。 `task<void>` 類型的工作不會產生任何結果。 工作可以獨立於其他工作，個別等候及取消。 它也包含與其他工作使用接續 ( `then`)，和聯結 ( `when_all`) 和選擇 ( `when_any`) 模式。  
  
## <a name="syntax"></a>語法  
  
```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```  
  
#### <a name="parameters"></a>參數  
 `T`  
 `T`  
 `_ReturnType`  
 此工作的結果類型。  
  
## <a name="members"></a>Members  
  
### <a name="public-typedefs"></a>公用 Typedefs  
  
|名稱|描述|  
|----------|-----------------|  
|`result_type`|此類別物件所產生的結果類型。|  
  
### <a name="public-constructors"></a>公用建構函式  
  
|名稱|說明|  
|----------|-----------------|  
|[工作](#ctor)|多載。 建構 `task` 物件。|  
  
### <a name="public-methods"></a>公用方法  
  
|名稱|描述|  
|----------|-----------------|  
|[get](#get)|多載。 傳回這個工作產生的結果。 如果工作不在終止狀態，則呼叫 `get` 將會等候工作完成。 在 `result_type` 為 `void` 的工作上被呼叫時，這個方法不會傳回值。|  
|[is_apartment_aware](#is_apartment_aware)|判斷工作是否解除包裝 Windows 執行階段 `IAsyncInfo` 介面或是從這類工作繼承而來。|  
|[is_done](#is_done)|判定工作是否完成。|  
|[排程器](#scheduler)|傳回此工作的排程器|  
|[然後](#then)|多載。 將接續工作加入至此工作。|  
|[等候](#wait)|等候這個工作到達終止狀態。 如果符合所有的工作相依性，而且未經選取供背景工作執行，則 `wait` 可以執行內嵌工作。|  
  
### <a name="public-operators"></a>公用運算子  
  
|名稱|說明|  
|----------|-----------------|  
|[operator!=](#operator_neq)|多載。 判斷兩個 `task` 物件是否表示不同的內部工作。|  
|[operator=](#operator_eq)|多載。 將某個 `task` 物件的內容取代為另一個物件的內容。|  
|[operator==](#operator_eq_eq)|多載。 判斷兩個 `task` 物件是否表示相同的內部工作。|  
  
## <a name="remarks"></a>備註  
 如需詳細資訊，請參閱[工作平行處理原則](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)。  
  
## <a name="inheritance-hierarchy"></a>繼承階層  
 `task`  
  
## <a name="requirements"></a>需求  
 **標頭︰** ppltasks.h  
  
 **命名空間：** concurrency  
  
##  <a name="get"></a>取得 

 傳回這個工作產生的結果。 如果工作不在終止狀態，則呼叫 `get` 將會等候工作完成。 在 `result_type` 為 `void` 的工作上被呼叫時，這個方法不會傳回值。  
  
```
_ReturnType get() const;

void get() const;
```  
  
### <a name="return-value"></a>傳回值  
 工作的結果。  
  
### <a name="remarks"></a>備註  
 如果工作已取消，呼叫`get`將會擲回[task_canceled](task-canceled-class.md)例外狀況。 如果工作發生不同的例外狀況，或例外狀況從前項工作傳播至它，則呼叫 `get` 將會擲回該例外狀況。  
  
> [!IMPORTANT]
>  在[!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)]應用程式中，請勿呼叫[concurrency::task::wait](#wait)或`get`(`wait`呼叫`get`) 會在 STA 執行的程式碼中 否則，執行階段擲回[concurrency:: invalid_operation](invalid-operation-class.md)因為這些方法會封鎖目前的執行緒，而且可能會導致應用程式沒有回應。 不過，您可以呼叫`get`方法，以接收前項工作的結果，因為會立即提供結果的工作為基礎的接續。  
  
##  <a name="is_apartment_aware"></a>is_apartment_aware 

 判斷工作是否解除包裝 Windows 執行階段 `IAsyncInfo` 介面或是從這類工作繼承而來。  
  
```
bool is_apartment_aware() const;
```  
  
### <a name="return-value"></a>傳回值  
 如果工作解除包裝 `true` 介面或是從這類工作繼承而來，則為 `IAsyncInfo`，否則為 `false`。  
  
##  <a name="is_done"></a>task:: is_done 方法 （並行執行階段）  
 判定工作是否完成。  
  
```
bool is_done() const;
```  
  
### <a name="return-value"></a>傳回值  
 如果工作已完成，false 否則則為 true。  
  
### <a name="remarks"></a>備註  
 如果工作已完成或已取消 （不論有無使用者例外狀況），則函數會傳回 true。  
  
##  <a name="operator_neq"></a>運算子 ！ = 

 判斷兩個 `task` 物件是否表示不同的內部工作。  
  
```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>參數  
 `_Rhs`  
  
### <a name="return-value"></a>傳回值  
 如果這些物件參考不同的基礎工作則為 `true`，否則為 `false`。  
  
##  <a name="operator_eq"></a>運算子 = 

 將某個 `task` 物件的內容取代為另一個物件的內容。  
  
```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```  
  
### <a name="parameters"></a>參數  
 `_Other`  
 來源 `task` 物件。  
  
### <a name="return-value"></a>傳回值  
  
### <a name="remarks"></a>備註  
 由於 `task` 的表現就像智慧型指標，因此在複製指派之後，這個 `task` 物件和 `_Other` 一樣，都表示相同的實際工作。  
  
##  <a name="operator_eq_eq"></a>運算子 = = 

 判斷兩個 `task` 物件是否表示相同的內部工作。  
  
```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>參數  
 `_Rhs`  
  
### <a name="return-value"></a>傳回值  
 如果這些物件參考相同的基礎工作則為 `true`，否則為 `false`。  
  
##  <a name="scheduler"></a>task:: scheduler 方法 （並行執行階段）  
 傳回此工作的排程器  
  
```
scheduler_ptr scheduler() const;
```  
  
### <a name="return-value"></a>傳回值  
 排程器指標  
  
##  <a name="ctor"></a>工作 

 建構 `task` 物件。  
  
```
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```  
  
### <a name="parameters"></a>參數  
 `T`  
 從中要建構工作的參數的類型。  
  
 `_Param`  
 從中要建構工作的參數。 如果您在 Windows 市集應用程式中使用工作，則此參數可以是 Lambda、函式物件、`task_completion_event<result_type>` 物件或 Windows::Foundation::IAsyncInfo。 Lambda 或函式物件應該是相當於 `std::function<X(void)>` 的類型，其中 X 可以是類型 `result_type`、`task<result_type>` 或 Windows 市集應用程式中 Windows::Foundation::IAsyncInfo 的變數。  
  
 `_TaskOptions`  
 工作選項包括取消語彙基元、排程器等等  
  
 `_Other`  
 來源 `task` 物件。  
  
### <a name="remarks"></a>備註  
 出現 `task` 的預設建構函式，只是為了讓工作在容器內使用。 只有在指派有效的工作給預設建構的工作之後，您才能使用它。 例如，方法`get`，`wait`或`then`將會擲回[invalid_argument](../../../standard-library/invalid-argument-class.md)預設建構的工作上被呼叫時的例外狀況。  
  
 從 `task_completion_event` 建立的工作，會在設定工作完成事件後完成 (並排定其接續作業)。  
  
 接受取消語彙基元的建構函式版本，會建立可以透過使用 `cancellation_token_source` (語彙基元取得來源) 取消的工作。 在沒有取消語彙基元的情況下建立的工作，無法取消。  
  
 從 `Windows::Foundation::IAsyncInfo` 介面或從傳回 `IAsyncInfo` 介面的 Lambda 建立的工作，當內含的 Windows 執行階段非同步作業或動作完成時，該工作會到達其終止狀態。 同樣地，從傳回 `task<result_type>` 的 Lambda 建立的工作，會在內部工作到達終止狀態時，而不是在 Lambda 傳回時，到達其終止狀態。  
  
 `task` 的行為就像智慧型指標，可透過傳值方式安全傳遞。 它可以由多個執行緒存取，而不需要鎖定。  
  
 接受 Windows::Foundation::IAsyncInfo 介面或傳回這類介面之 Lambda 的建構函式多載，只供 Windows 市集應用程式使用。  
  
 如需詳細資訊，請參閱[工作平行處理原則](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)。  
  
##  <a name="then"></a>然後 

 將接續工作加入至此工作。  
  
```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```   
  
### <a name="parameters"></a>參數  
 `_Function`  
 此工作會叫用的函式物件的類型。  
  
 `_Func`  
 當這個工作完成時執行的接續函式。 這個接續函式必須接受 `result_type` 或 `task<result_type>` 的變數做為輸入，其中 `result_type` 是這個工作所產生結果的類型。  
  
 `_TaskOptions`  
 工作選項包括取消語彙基元、排程器和接續內容。 前 3 個選項預設會從前項工作繼承  
  
 `_CancellationToken`  
 要與接續工作產生關聯的取消語彙基元。 所建立不含取消語彙基元的接續工作將會繼承其前項工作的語彙基元。  
  
 `_ContinuationContext`  
 指定執行接續作業位置的變數。 在 Windows 市集樣式應用程式中使用時，此變數才能發揮效用。 如需詳細資訊，請參閱[task_continuation_context](task-continuation-context-class.md)  
  
### <a name="return-value"></a>傳回值  
 新建立的接續工作。 所傳回工作的結果類型取決於 `_Func` 傳回哪些項目。  
  
### <a name="remarks"></a>備註  
 可接受傳回 Windows::Foundation::IAsyncInfo 介面的 Lambda 或仿函數 (functor) 之 `then` 的多載，只供 Windows 市集應用程式使用。  
  
 如需有關如何使用接續工作組成非同步工作的詳細資訊，請參閱[工作平行處理原則](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)。  
  
##  <a name="wait"></a>等候 

 等候這個工作到達終止狀態。 如果符合所有的工作相依性，而且未經選取供背景工作執行，則 `wait` 可以執行內嵌工作。  
  
```
task_status wait() const;
```  
  
### <a name="return-value"></a>傳回值  
 可能是 `task_status` 或 `completed` 的 `canceled` 值。 如果工作在執行時發生例外狀況，或例外狀況從前項工作傳播至它，則 `wait` 將會擲回該例外狀況。  
  
### <a name="remarks"></a>備註  
  
> [!IMPORTANT]
>  在[!INCLUDE[win8_appname_long](../../../build/includes/win8_appname_long_md.md)]應用程式中，請勿呼叫`wait`在 STA 執行的程式碼 否則，執行階段擲回[concurrency:: invalid_operation](invalid-operation-class.md)因為這個方法會封鎖目前的執行緒，而且可能會導致應用程式沒有回應。 不過，您可以呼叫[concurrency](#get)方法，以工作為基礎的接續接收前項工作的結果。  
  
## <a name="see-also"></a>另請參閱  
 [concurrency 命名空間](concurrency-namespace.md)
