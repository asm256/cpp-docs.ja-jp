---
title: "is_nothrow_constructible クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 2ff20de3656cde44d79936c6bf1374134eb95068
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible クラス
指定された引数型の使用時に型を構築できるかどうか、およびスローしないと判明しているかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T, class... Args>  
struct is_nothrow_constructible;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
 `Args`  
 `T` のコンストラクター内の一致させる引数型。  
  
## <a name="remarks"></a>コメント  
 型の述語のインスタンスは、型 `T` が `Args` の引数型を使用して構築可能であり、コンストラクターがスローしないとコンパイラによって認識されている場合 true を保持します。それ以外の場合は false を保持します。 型 `T` を構築できるのは、変数定義 `T t(std::declval<Args>()...);` が整形式である場合です。 `T` と `Args` のすべての型は両方とも、完全な型、`void`、または不明なバインドの配列にする必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)




