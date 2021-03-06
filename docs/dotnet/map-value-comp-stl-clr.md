---
title: "map::value_comp (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::map::value_comp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_comp メンバー [STL/CLR]"
ms.assetid: b0e53052-f3cc-48c8-8e29-1b151c23860a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# map::value_comp (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

2 要素の値の順序のデリゲートをコピーします。  
  
## 構文  
  
```  
value_compare^ value_comp();  
```  
  
## 解説  
 このメンバー関数は、被制御シーケンスの並べ替えに使用されるごとにデリゲートを返します。  2 要素の値を比較するときに使用します。  
  
## 使用例  
  
```  
// cliext_map_value_comp.cpp   
// compile with: /clr   
#include <cliext/map>   
  
typedef cliext::map<wchar_t, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    Mymap::value_compare^ kcomp = c1.value_comp();   
  
    System::Console::WriteLine("compare([L'a', 1], [L'a', 1]) = {0}",   
        kcomp(Mymap::make_value(L'a', 1),   
            Mymap::make_value(L'a', 1)));   
    System::Console::WriteLine("compare([L'a', 1], [L'b', 2]) = {0}",   
        kcomp(Mymap::make_value(L'a', 1),   
            Mymap::make_value(L'b', 2)));   
    System::Console::WriteLine("compare([L'b', 2], [L'a', 1]) = {0}",   
        kcomp(Mymap::make_value(L'b', 2),   
            Mymap::make_value(L'a', 1)));   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **\(\[\] L'a、1、1、L'a \[\]\) \= false を比較します。**  
**\(\[\] L'a、1、2、L'b \[\]\) \= True を比較します。**  
**\(\[\] L'b、2、1、L'a \[\]\) \= false を比較します。**   
## 必要条件  
 **ヘッダー:** の \<cliext\/マップ\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [マップ](../dotnet/map-stl-clr.md)   
 [map::value\_compare](../dotnet/map-value-compare-stl-clr.md)   
 [map::value\_type](../dotnet/map-value-type-stl-clr.md)