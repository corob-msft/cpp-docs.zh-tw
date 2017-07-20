---
title: "operator!= (map) (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator!= 成員 [STL/CLR]"
ms.assetid: 335c3b24-27ed-4cc8-b49d-02b83ec5fd0b
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator!= (map) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

清單不相等比較。  
  
## 語法  
  
```  
template<typename Key,  
    typename Mapped>  
    bool operator!=(map<Key, Mapped>% left,  
        map<Key, Mapped>% right);  
```  
  
#### 參數  
 left  
 要比較的左邊容器。  
  
 right  
 要比較的右邊容器。  
  
## 備註  
 運算子函式會傳回 `!(``left` `==` `right``)`。  您可用它來測試這兩個對應逐一比較項目時， `left` 是否與 `right` 排序相同。  
  
## 範例  
  
```  
// cliext_map_operator_ne.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    c1.insert(Mymap::make_value(L'a', 1));   
    c1.insert(Mymap::make_value(L'b', 2));   
    c1.insert(Mymap::make_value(L'c', 3));   
  
// display contents " [a 1] [b 2] [c 3]"   
    for each (Mymap::value_type elem in c1)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
// assign to a new container   
    Mymap c2;   
    c2.insert(Mymap::make_value(L'a', 1));   
    c2.insert(Mymap::make_value(L'b', 2));   
    c2.insert(Mymap::make_value(L'd', 4));   
  
// display contents " [a 1] [b 2] [d 4]"   
    for each (Mymap::value_type elem in c2)   
        System::Console::Write(" [{0} {1}]", elem->first, elem->second);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] != [a b c] is {0}",   
        c1 != c1);   
    System::Console::WriteLine("[a b c] != [a b d] is {0}",   
        c1 != c2);   
    return (0);   
    }  
  
```  
  
  **\[a 1\] \[b 2\] \[c 3\]**  
 **\[a 1\] \[b 2\] \[d 4\]**  
**\[a b c\] \!\= \[a b c\] is False**  
**\[a b c\] \!\= \[a b d\] is True**   
## 需求  
 **標頭：** \<cliext\/map\>  
  
 **命名空間：** cliext  
  
## 請參閱  
 [map](../dotnet/map-stl-clr.md)   
 [operator\=\= \(map\)](../dotnet/operator-equality-map-stl-clr.md)   
 [operator\< \(map\)](../dotnet/operator-less-than-map-stl-clr.md)   
 [operator\>\= \(map\)](../dotnet/operator-greater-or-equal-map-stl-clr.md)   
 [operator\> \(map\)](../dotnet/operator-greater-than-map-stl-clr.md)   
 [operator\<\= \(map\)](../dotnet/operator-less-or-equal-map-stl-clr.md)