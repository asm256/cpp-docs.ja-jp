---
title: '&lt;utility&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <utility>
dev_langs: C++
helpviewer_keywords: utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e89fdf2b1af11b40c13f57b0febd1daa05894ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltutilitygt"></a>&lt;utility&gt;
C++ 標準ライブラリの型、関数、および演算子を定義し、オブジェクトのペアを作成し管理するのに役立てます。これらは 2 つのオブジェクトをあたかも 1 つのように扱う必要がある場合に役立ちます。  
  
## <a name="syntax"></a>構文  
  
```  
#include <utility>  
  
```  
  
## <a name="remarks"></a>コメント  
 ペアは、C++ 標準ライブラリで広く使用されます。 これはさまざまな関数の引数と戻り値として、また [map クラス](../standard-library/map-class.md)と [multimap クラス](../standard-library/multimap-class.md)などのコンテナーの要素型として必要です。 \<utility> ヘッダーは、キー/値ペア型の要素の管理を補助するために、\<map> により自動で追加されます。  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|`pair` 要素の型をラップするクラスです。|  
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|`pair` 要素の数をラップするクラスです。|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[forward](../standard-library/utility-functions.md#forward)|引数の参照型 (`lvalue` または `rvalue` のどちらか) が完全転送によって隠されないよう保ちます。|  
|[get](../standard-library/utility-functions.md#get)|`pair` オブジェクトから要素を取得する関数です。|  
|[make_pair](../standard-library/utility-functions.md#make_pair)|`pair` 型のオブジェクトを作成するために使用されるテンプレート ヘルパー関数。コンポーネントの型は、パラメーターとして渡されるデータ型に基づいています。|  
|[move](../standard-library/utility-functions.md#move)|`rvalue` 参照として引数で渡されたものを返します。|  
|[swap](../standard-library/utility-functions.md#swap)|2 つの `pair` オブジェクトの要素を交換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator!=](../standard-library/utility-operators.md#op_neq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しくないかどうかを調べます。|  
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトと等しいかどうかを調べます。|  
|[operator<](../standard-library/utility-operators.md#op_lt)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより小さいかどうかを調べます。|  
|[operator\<=](../standard-library/utility-operators.md#op_gt_eq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以下かどうかを調べます。|  
|[operator>](../standard-library/utility-operators.md#op_gt)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクトより大きいかどうかを調べます。|  
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|演算子の左辺のペア オブジェクトが右辺のペア オブジェクト以上かどうかを調べます。|  
  
### <a name="structs"></a>構造体  
  
|||  
|-|-|  
|[identity](../standard-library/identity-structure.md)||  
|[pair](../standard-library/pair-structure.md)|2 つのオブジェクトを 1 つのオブジェクトとして処理する機能を提供する型。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



