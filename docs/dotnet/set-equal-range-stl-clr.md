---
title: "set::equal_range (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::set::equal_range
dev_langs: C++
helpviewer_keywords: equal_range member [STL/CLR]
ms.assetid: f0b20a65-f37a-44b1-a291-09c33c10c355
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 47078cca08ed8f2ccdea13e1d9df3db0ed9fea1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="setequalrange-stlclr"></a>set::equal_range (STL/CLR)
指定したキーに一致する範囲を検索します。  
  
## <a name="syntax"></a>構文  
  
```  
cliext::pair<iterator, iterator> equal_range(key_type key);  
```  
  
#### <a name="parameters"></a>パラメーター  
 key  
 検索対象のキー値。  
  
## <a name="remarks"></a>コメント  
 このメンバー関数が組の反復子を返します`cliext::pair<iterator, iterator>(` [set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md) `(key),` [set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)`(key))`です。 使用する指定したキーと一致する、被制御シーケンスの現在の要素の範囲が決まります。  
  
## <a name="example"></a>例  
  
```  
// cliext_set_equal_range.cpp   
// compile with: /clr   
#include <cliext/set>   
  
typedef cliext::set<wchar_t> Myset;   
typedef Myset::pair_iter_iter Pairii;   
int main()   
    {   
    Myset c1;   
    c1.insert(L'a');   
    c1.insert(L'b');   
    c1.insert(L'c');   
  
// display initial contents " a b c"   
    for each (wchar_t elem in c1)   
        System::Console::Write(" {0}", elem);   
    System::Console::WriteLine();   
  
// display results of failed search   
    Pairii pair1 = c1.equal_range(L'x');   
    System::Console::WriteLine("equal_range(L'x') empty = {0}",   
        pair1.first == pair1.second);   
  
// display results of successful search   
    pair1 = c1.equal_range(L'b');   
    for (; pair1.first != pair1.second; ++pair1.first)   
        System::Console::Write(" {0}", *pair1.first);   
    System::Console::WriteLine();   
    return (0);   
    }  
  
```  
  
```Output  
 a b c  
equal_range(L'x') empty = True  
 b  
```  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext と set >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [設定 (STL/CLR)](../dotnet/set-stl-clr.md)   
 [set::count (STL/CLR)](../dotnet/set-count-stl-clr.md)   
 [set::find (STL/CLR)](../dotnet/set-find-stl-clr.md)   
 [set::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md)   
 [set::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)