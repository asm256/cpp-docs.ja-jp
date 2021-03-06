---
title: "operator&lt; (vector) (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::vector::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator< メンバー [STL/CLR]"
ms.assetid: 41fbd028-e937-4337-9429-57e79a993eef
caps.latest.revision: 18
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# operator&lt; (vector) (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ベクターより小さい\) を比較します。  
  
## 構文  
  
```  
template<typename Value>  
    bool operator<(vector<Value>% left,  
        vector<Value>% right);  
```  
  
#### パラメーター  
 \[left\]  
 比較の左辺のコンテナー。  
  
 \[right\]  
 比較の右辺のコンテナー。  
  
## 解説  
 演算子関数は、`!(``right``[i] <``left``[i])` が当てはまります。また、`left``[i] <``right``[i]`最小位置 `i` の場合、true を返します。  それ以外の点では、2 種類のベクターが要素によって比較された要素の場合 `left` は `right` の前に並べるかをテストするときに使用する `left``->size() <``right``->size()` を返します。  
  
## 使用例  
  
```  
// cliext_vector_operator_lt.cpp   
// compile with: /clr   
#include <cliext/vector>   
  
int main()   
    {   
    cliext::vector<wchar_t> c1;   
    c1.push_back(L'a');   
    c1.push_back(L'b');   
    c1.push_back(L'c');   
  
// display contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// assign to a new container   
    cliext::vector<wchar_t> c2;   
    c2.push_back(L'a');   
    c2.push_back(L'b');   
    c2.push_back(L'd');   
  
// display contents " a b d"   
    for each (wchar_t elem in c2)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
    System::Console::WriteLine("[a b c] < [a b c] is {0}",   
        c1 < c1);   
    System::Console::WriteLine("[a b c] < [a b d] is {0}",   
        c1 < c2);   
    return (0);   
    }  
  
```  
  
  **b c**  
 **b d**  
**b c \[\] \< \[\] b c false です。**  
**b \[\] \< \[\] b c d 当てはまります。**   
## 必要条件  
 **ヘッダー:** の \<cliext とベクター\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [ベクター](../dotnet/vector-stl-clr.md)   
 [operator\=\= \(vector\)](../Topic/operator==%20\(vector\)%20\(STL-CLR\).md)   
 [operator\!\= \(vector\)](../Topic/operator!=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\>\= \(vector\)](../Topic/operator%3E=%20\(vector\)%20\(STL-CLR\).md)   
 [operator\> \(vector\)](../dotnet/operator-greater-than-vector-stl-clr.md)   
 [operator\<\= \(vector\)](../dotnet/operator-less-or-equal-vector-stl-clr.md)