---
title: "hash_multimap::value_compare (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multimap::value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare メンバー [STL/CLR]"
ms.assetid: 64daa1b6-3019-4850-9ec5-ae63c01fe819
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# hash_multimap::value_compare (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 要素の値の順序のデリゲート。  
  
## 構文  
  
```  
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>  
    value_compare;  
```  
  
## 解説  
 型は値の引数の順序を決定するデリゲートのシノニムです。  
  
## 使用例  
  
```  
// cliext_hash_multimap_value_compare.cpp   
// compile with: /clr   
#include <cliext/hash_map>   
  
typedef cliext::hash_map<wchar_t, int> Myhash_multimap;   
int main()   
    {   
    Myhash_multimap c1;   
    Myhash_multimap::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Myhash_multimap::make_value(L'a', 1),   
            Myhash_multimap::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Myhash_multimap::make_value(L'a', 1),   
            Myhash_multimap::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Myhash_multimap::make_value(L'b', 2),   
            Myhash_multimap::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\(\[\] L'a、1、1、L'a \[\]\) \= True を比較します。**  
**\(\[\] L'a、1、2、L'b \[\]\) \= True を比較します。**  
**\(\[\] L'b、2、1、L'a \[\]\) \= false を比較します。**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_map\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multimap](../dotnet/hash-multimap-stl-clr.md)   
 [hash\_multimap::key\_compare](../dotnet/hash-multimap-key-compare-stl-clr.md)   
 [hash\_multimap::value\_comp](../dotnet/hash-multimap-value-comp-stl-clr.md)   
 [hash\_multimap::value\_type](../dotnet/hash-multimap-value-type-stl-clr.md)