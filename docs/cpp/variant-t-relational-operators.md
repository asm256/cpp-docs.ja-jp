---
title: "_variant_t 関係演算子 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs: C++
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: eacfe9584cedfd45a952dca62dae545f617b1433
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="variantt-relational-operators"></a>_variant_t 関係演算子
**Microsoft 固有の仕様**  
  
 2 つの `_variant_t` オブジェクトを比較して、等しいかどうかを確認します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      bool operator==(  
   const VARIANT& varSrc   
) const;  
bool operator==(  
   const VARIANT* pSrc   
) const;  
bool operator!=(  
   const VARIANT& varSrc   
) const;  
bool operator!=(  
   const VARIANT* pSrc   
) const;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *varSrc*  
 A**バリアント**と比較する、`_variant_t`オブジェクト。  
  
 `pSrc`  
 ポインター、**バリアント**と比較する、`_variant_t`オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 返します**true**比較が保持している場合**false**しない場合。  
  
## <a name="remarks"></a>コメント  
 比較、`_variant_t`オブジェクトを**バリアント**等しいかどうかをテストします。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)