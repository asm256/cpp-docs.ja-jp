---
title: "hash_multiset::key_type (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::hash_multiset::key_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "key_type メンバー [STL/CLR]"
ms.assetid: e3888fa3-5daf-4fc6-acf3-df7215c5d9ff
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# hash_multiset::key_type (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

順序付けキーの型です。  
  
## 構文  
  
```  
typedef Key key_type;  
```  
  
## 解説  
 この型は、テンプレート パラメーター `Key` のシノニムです。  
  
## 使用例  
  
```  
// cliext_hash_multiset_key_type.cpp   
// compile with: /clr   
#include <cliext/hash_set>   
  
typedef cliext::hash_multiset<wchar_t> Myhash_multiset;   
int main()   
    {   
    Myhash_multiset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display contents " a b c" using key_type   
    for (Myhash_multiset::iterator it = c1.begin(); it != c1.end(); ++it)   
        {   // store element in key_type object   
        Myhash_multiset::key_type val = *it;   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
  **b c**   
## 必要条件  
 **ヘッダー:** の \<cliext\/hash\_set\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [hash\_multiset](../dotnet/hash-multiset-stl-clr.md)   
 [hash\_multiset::key\_compare](../dotnet/hash-multiset-key-compare-stl-clr.md)   
 [hash\_multiset::value\_type](../dotnet/hash-multiset-value-type-stl-clr.md)