---
title: "stack::value_type (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack::value_type
dev_langs: C++
helpviewer_keywords: value_type member [STL/CLR]
ms.assetid: 867ff1a7-c91c-4168-9b85-21fd0dcf4806
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 24e3cc0d992f6c955f2fa4154591b8c679a376f5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="stackvaluetype-stlclr"></a>stack::value_type (STL/CLR)
要素の型。  
  
## <a name="syntax"></a>構文  
  
```  
typedef Value value_type;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Value`のシノニムです。  
  
## <a name="example"></a>例  
  
```  
// cliext_stack_value_type.cpp   
// compile with: /clr   
#include <cliext/stack>   
  
typedef cliext::stack<wchar_t> Mystack;   
int main()   
    {   
    Mystack c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display reversed contents " a b c" using value_type   
    for (; !c1.empty(); c1.pop())   
        {   // store element in value_type object   
        Mystack::value_type val = c1.top();   
  
        System::Console::Write(" {0}", val);   
        }   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c b a  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [スタック (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [stack::const_reference (STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)   
 [stack::reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)