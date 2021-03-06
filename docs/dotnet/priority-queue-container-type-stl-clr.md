---
title: "priority_queue::container_type (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::priority_queue::container_type
dev_langs: C++
helpviewer_keywords: container_type member [STL/CLR]
ms.assetid: 97d79791-53cb-48f9-a139-69502517569f
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 83041a535ae1b7e07fecf2dc20e053fa633783d2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="priorityqueuecontainertype-stlclr"></a>priority_queue::container_type (STL/CLR)
基になるコンテナーの型。  
  
## <a name="syntax"></a>構文  
  
```  
typedef Container value_type;  
```  
  
## <a name="remarks"></a>コメント  
 この型は、テンプレート パラメーター `Container`のシノニムです。  
  
## <a name="example"></a>例  
  
```  
// cliext_priority_queue_container_type.cpp   
// compile with: /clr   
#include <cliext/queue>   
  
typedef cliext::priority_queue<wchar_t> Mypriority_queue;   
int main()   
    {   
    Mypriority_queue c1;   
    c1.push(L'a');   
    c1.push(L'b');   
    c1.push(L'c');   
  
// display contents " a b c" using container_type   
    Mypriority_queue::container_type wc1 = c1.get_container();   
    for each (wchar_t elem in wc1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
c a b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/キュー >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [priority_queue::get_container (STL/CLR)](../dotnet/priority-queue-get-container-stl-clr.md)