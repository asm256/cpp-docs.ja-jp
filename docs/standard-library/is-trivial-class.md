---
title: "is_trivial クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_trivial
dev_langs: C++
helpviewer_keywords: is_trivial
ms.assetid: 6beb11d4-2f38-4c7e-9959-ca5d26250df7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7837237d88833fdfdc3a82df0590a990480847d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="istrivial-class"></a>is_trivial クラス
型が単純型であるかどうかをテストします。  
  
## <a name="syntax"></a>構文  
  
```
template <class T>  
struct is_trivial;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 照会する型。  
  
## <a name="remarks"></a>コメント  
 型 `T` が単純型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 単純型は、スカラー型、普通にコピー可能なクラス型、これらの型の配列と、これらの型の cv-qualified バージョンです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<type_traits>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [<type_traits>](../standard-library/type-traits.md)



