---
title: "stack::size (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::size
dev_langs: C++
helpviewer_keywords: size member [STL/CLR]
ms.assetid: 6113e649-a4f9-4021-8131-34cee4bc8ca0
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c43a16e897e2517ccac0597512b741cb3e66a6ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="stacksize-stlclr"></a>stack::size (STL/CLR)
要素の数をカウントします。  
  
## <a name="syntax"></a>構文  
  
```  
size_type size();  
```  
  
## <a name="remarks"></a>コメント  
 このメンバー関数は、被制御シーケンスの長さを返します。 これを使用するには、被制御シーケンス内の現在の要素の数を決定します。 シーケンスが参照してください、0 以外のサイズを持つかどうかは、関心のあるすべて場合[stack::empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)`()`です。  
  
## <a name="example"></a>例  
  
```  
// cliext_stack_size.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1.get_container())   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());   
  
// pop an item and reinspect   
    c1.pop();   
    System::Console::WriteLine("size() = {0} after popping", c1.size());   
  
// add two elements and reinspect   
    c1.push(L'a');   
    c1.push(L'b');   
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
size() = 3 starting with 3  
size() = 2 after popping  
size() = 4 after adding 2  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)