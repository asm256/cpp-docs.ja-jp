---
title: "add_const クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::add_const
dev_langs: C++
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d0f4baf1e9cb6a740cddc0739bb13b35e6a0a684
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="addconst-class"></a>add_const クラス
型から const 型を作成します。  
  
## <a name="syntax"></a>構文  
  
```  
template <class Ty>  
struct add_const;
```  
  
#### <a name="parameters"></a>パラメーター  
 `Ty`  
 変更する型。  
  
## <a name="remarks"></a>コメント  
 この型修飾子のインスタンスは、`Ty` が参照、関数、または const で修飾された型である場合は、修飾型 `Ty` を保持します。それ以外の場合は、`const Ty` を保持します。  
  
## <a name="example"></a>例  
  
```cpp  
// std__type_traits__add_const.cpp   
// compile with: /EHsc   
#include <type_traits>   
#include <iostream>   
  
int main()   
{   
    std::add_const<int>::type *p = (const int *)0;   
  
    p = p;  // to quiet "unused" warning   
    std::cout << "add_const<int> == "   
        << typeid(*p).name() << std::endl;   
  
    return (0);   
}  
```  
  
```Output  
add_const<int> == int  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)   
 [remove_const クラス](../standard-library/remove-const-class.md)
