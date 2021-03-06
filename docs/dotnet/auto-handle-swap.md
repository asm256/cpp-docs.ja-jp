---
title: "auto_handle::swap | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::auto_handle::swap"
  - "auto_handle.swap"
  - "auto_handle::swap"
  - "msclr..auto_handle.swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::swap"
ms.assetid: 3ebf82d7-9b69-4a72-a22d-69b4f640f9b0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# auto_handle::swap
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

別の `auto_handle`の交換オブジェクト。  
  
## 構文  
  
```  
void swap(  
   auto_handle<_element_type> % _right  
);  
```  
  
#### パラメーター  
 `_right`  
 オブジェクトを交換する `auto_handle`。  
  
## 使用例  
  
```  
// msl_auto_handle_swap.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   s1.swap( s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
  **s1 \= 「String 1 " s2 \= 「String 2」**  
**s1 \= 「String 2 " s2 \= 「String 1」**   
## 必要条件  
 **ヘッダー ファイル** \<msclr\\auto\_handle.h\>  
  
 **名前空間** の msclr  
  
## 参照  
 [auto\_handle Members](../dotnet/auto-handle-members.md)   
 [swap 関数 \(auto\_handle\)](../dotnet/swap-function-auto-handle.md)