---
title: "adjacent_difference (STL/CLR) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::adjacent_difference
dev_langs: C++
helpviewer_keywords: adjacent_difference function
ms.assetid: 2b462e2e-b8f2-4b2e-9b87-5f688d8da9f4
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0be63f7032de5f6d3def4ba74f24a346785b7391
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="adjacentdifference-stlclr"></a>adjacent_difference (STL/CLR)
入力範囲内の各要素とその先行要素との連続する差分を計算し、結果をターゲット範囲に出力するか、または差分演算が指定された別の二項演算に置き換えられた汎用化されたプロシージャの結果を計算します。  
  
## <a name="syntax"></a>構文  
  
```  
template<class _InIt, class _OutIt> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest);  
template<class _InIt, class _OutIt, class _Fn2> inline  
    _OutIt adjacent_difference(_InIt _First, _InIt _Last,  
        _OutIt _Dest, _Fn2 _Func);  
```  
  
## <a name="remarks"></a>コメント  
 この関数の動作は、C++ 標準ライブラリの数値関数と同じ`adjacent_difference`です。 詳細については、次を参照してください。 [adjacent_difference](../standard-library/numeric-functions.md#adjacent_difference)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<cliext/numeric >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>関連項目  
 [numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)