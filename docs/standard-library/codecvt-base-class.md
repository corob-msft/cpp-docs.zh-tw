---
title: "codecvt_base 類別 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt_base
- xlocale/std::codecvt_base
dev_langs:
- C++
helpviewer_keywords:
- codecvt_base class
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 20
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: d0c12f0dfb1b0ceb111f3c3313e78dd5c9197f70
ms.contentlocale: zh-tw
ms.lasthandoff: 04/29/2017

---
# <a name="codecvtbase-class"></a>codecvt_base 類別
codecvt 類別的基底類別，用來定義當做 **result** 參考的列舉類型，用作 facet 成員函式的傳回型別以表示轉換結果。  
  
## <a name="syntax"></a>語法  
  
```
class codecvt_base : public locale::facet {
public:
    enum result {ok, partial, error, noconv};
    codecvt_base( size_t _Refs = 0);
    bool always_noconv() const;
    int max_length() const;
    int encoding() const;
    ~codecvt_base()

protected:
    virtual bool do_always_noconv() const;
    virtual int do_max_length() const;
    virtual int do_encoding() const;
};
```  
  
## <a name="remarks"></a>備註  
 此類別描述樣板類別 [codecvt](../standard-library/codecvt-class.md) 之所有特製化通用的列舉。 列舉結果描述可能從 [do_in](../standard-library/codecvt-class.md#do_in) 或 [do_out](../standard-library/codecvt-class.md#do_out) 傳回的值：  
  
- 如果內部和外部字元編碼之間的轉換成功，則為 **ok**。  
  
- 如果目的地不夠大，無法成功轉換，則為 **partial**。  
  
- 如果來源序列的格式不正確，則為 **error**。  
  
- 如果函式不會執行任何轉換，則為 **noconv**。  
  
## <a name="requirements"></a>需求  
 **標頭︰**\<locale>  
  
 **命名空間：** std  
  
## <a name="see-also"></a>另請參閱  
 [C++ 標準程式庫中的執行緒安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)



