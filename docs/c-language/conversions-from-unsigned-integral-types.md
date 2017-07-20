---
title: "從不帶正負號整數類型的轉換 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "資料類型轉換 [C++], 帶正負號和不帶正負號的整數"
  - "整數, 轉換"
  - "整數轉換, 從不帶正負號"
  - "類型轉換, 和整數相關"
  - "類型轉換 [C++], 帶正負號和不帶正負號的整數"
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 從不帶正負號整數類型的轉換
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

不帶正負號的整數會藉由截斷高序位位元，轉換為較短的不帶正負號或帶正負號的整數，或是藉由零擴充轉換為較長的不帶正負號或帶正負號的整數 \(請參閱[從不帶正負號的整數類型轉換](#_clang_table_4..3)表格\)。  
  
 當值使用的是降級至大小較小的帶正負號整數，或者不帶正負號整數時，會將其轉換為對應的帶正負號整數，如果可以由新的類型表示，其值是不變的。  不過，如果設定了正負號位元，則其值會改變，如下列範例所述。  
  
```  
int j;  
unsigned short k = 65533;  
  
j = k;  
printf_s( "%hd\n", j );   // Prints -3  
```  
  
 如果無法表示其值，則結果是由實作定義。  如需 Microsoft C 編譯器處理整數降級的詳細資訊，請參閱[類型轉換的轉換方式](../c-language/type-cast-conversions.md)。  從整數進行轉換，或轉換整數的類型也會導致相同的行為。  
  
 不帶正負號的值會以保留其值的方法進行轉換，而其無法直接在 C 中表示。  唯一的例外是從 `unsigned long` 轉換為 **float**，其中最多只會遺失低序位位元。  否則，會將值保存為帶正負號或不帶正負號的值。  當整數類資料類型的值轉換成浮動類型時，且其值無法顯示，則結果會是未定義。\(如需整數類資料和浮動類型範圍的詳細資訊，請參閱[基本類型的儲存區](../c-language/storage-of-basic-types.md)\)。  
  
 下表摘要說明從不帶正負號整數類資料類型進行轉換。  
  
### 從不帶正負號的整數類型轉換  
  
|從|轉換為|方法|  
|-------|---------|--------|  
|`unsigned char`|`char`|保留位元模式，高序位位元會變成正負號位元|  
|`unsigned char`|**short**|零擴充|  
|`unsigned char`|**long**|零擴充|  
|`unsigned char`|**unsigned short**|零擴充|  
|`unsigned char`|`unsigned long`|零擴充|  
|`unsigned char`|**float**|轉換為 **long**，將 **long** 轉換為 **float**|  
|`unsigned char`|**double**|轉換為 **long**，將 **long** 轉換為 **double**|  
|`unsigned char`|`long double`|轉換為 **long**，將 **long** 轉換為 **double**|  
|**unsigned short**|`char`|保留低序位位元組|  
|**unsigned short**|**short**|保留位元模式，高序位位元會變成正負號位元|  
|**unsigned short**|**long**|零擴充|  
|**unsigned short**|`unsigned char`|保留低序位位元組|  
|**unsigned short**|`unsigned long`|零擴充|  
|**unsigned short**|**float**|轉換為 **long**，將 **long** 轉換為 **float**|  
|**unsigned short**|**double**|轉換為 **long**，將 **long** 轉換為 **double**|  
|**unsigned short**|`long double`|轉換為 **long**，將 **long** 轉換為 **double**|  
|`unsigned long`|`char`|保留低序位位元組|  
|`unsigned long`|**short**|保留低序位字組|  
|`unsigned long`|**long**|保留位元模式，高序位位元會變成正負號位元|  
|`unsigned long`|`unsigned char`|保留低序位位元組|  
|`unsigned long`|**unsigned short**|保留低序位字組|  
|`unsigned long`|**float**|轉換為 **long**，將 **long** 轉換為 **float**|  
|`unsigned long`|**double**|直接轉換為 **double**|  
|`unsigned long`|`long double`|轉換為 **long**，將 **long** 轉換為 **double**|  
  
 **Microsoft 特定的**  
  
 對於 Microsoft 32 位元 C 編譯器，`unsigned int` 類型相當於 `unsigned long` 類型。  `unsigned int` 值的轉換與 `unsigned long` 的轉換使用相同的方式進行。  如果要轉換的值大於 signed **long** 的正數值，則從 `unsigned long` 值轉換為 **float** 會變得不精確。  
  
 **END Microsoft 特定的**  
  
## 請參閱  
 [指派轉換](../c-language/assignment-conversions.md)