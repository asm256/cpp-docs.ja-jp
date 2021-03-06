---
title: "unary_delegate_noreturn (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::unary_delegate_noreturn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unary_delegate_noreturn 関数 [STL/CLR]"
ms.assetid: 3c3fb143-f60f-4e28-a66b-690e3a7b2f9b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# unary_delegate_noreturn (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

genereic クラスは、1 引数のデリゲートを返します `void`説明します。  引数の型を使用して、指定するデリゲートを使用します。  
  
## 構文  
  
```  
generic<typename Arg>  
    delegate void unary_delegate_noreturn(Arg);  
```  
  
#### パラメーター  
 引数  
 引数の型。  
  
## 解説  
 genereic デリゲートは、その 1 引数を関数の戻り `void`説明します。  
  
 これで T: System.ComponentModel.IComponent  
  
 `unary_delegare_noreturn<int> Fun1;`  
  
 `unary_delegare_noreturn<int> Fun2;`  
  
 では、型 `Fun1` と `Fun2` はシノニムです:  
  
 `delegate void Fun1(int);`  
  
 `delegate void Fun2(int);`  
  
 これらは同じデータ型ではありません。  
  
## 使用例  
  
```  
// cliext_unary_delegate_noreturn.cpp   
// compile with: /clr   
#include <cliext/functional>   
  
void hash_val(wchar_t val)   
    {   
    System::Console::WriteLine("hash({0}) = {1}",   
       val, (val * 17 + 31) % 67);   
    }   
  
typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;   
int main()   
    {   
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);   
  
    myhash(L'a');   
    myhash(L'b');   
    return (0);   
    }  
  
```  
  
  **ハッシュ \(a\) \= 5**  
**ハッシュ \(b\) \= 22**   
## 必要条件  
 **ヘッダー:** の \<cliext と機能\>  
  
 **名前空間:** の cliext  
  
## 参照  
 [binary\_delegate](../Topic/binary_delegate%20\(STL-CLR\).md)   
 [binary\_delegate\_noreturn](../dotnet/binary-delegate-noreturn-stl-clr.md)   
 [unary\_delegate](../dotnet/unary-delegate-stl-clr.md)