---
title: "mem_fun_t クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: xfunctional/std::mem_fun_t
dev_langs: C++
helpviewer_keywords: mem_fun_t class
ms.assetid: 242566d4-750c-4c87-9d63-2e2c9d19ca2a
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b296e63f3392c6ba9a38116a096d8fd9526103e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="memfunt-class"></a>mem_fun_t クラス
ポインター引数による初期化を行うときに、引数を使用しない **non_const** メンバー関数を単項関数オブジェクトとして呼び出せるようにするアダプター クラス。  
  
## <a name="syntax"></a>構文  
  
```
template <class Result, class Type>
class mem_fun_t : public unary_function<Type *, Result> {
    explicit mem_fun_t(Result (Type::* _Pm)());

    Result operator()(Type* _Pleft) const;

 };
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Pm`  
 関数オブジェクトに変換される **Type** クラスのメンバー関数へのポインター。  
  
 `_Pleft`  
 `_Pm` メンバー関数が呼び出されるオブジェクト。  
  
## <a name="return-value"></a>戻り値  
 適合可能な単項関数。  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは `_Pm` のコピーをプライベート メンバー オブジェクトに格納します。これは、クラス **Type** のメンバー関数へのポインターである必要があります。 そのメンバー関数 `operator()` は ( `_Pleft`->* `_Pm`)( ) を返すように定義されています。  
  
## <a name="example"></a>例  
 `mem_fun_t` のコンストラクターは通常は直接使用されません。ヘルパー関数 `mem_fun` を使用してメンバー関数を適合させます。 メンバー関数アダプターの使用例については、「[mem_fun](../standard-library/functional-functions.md#mem_fun)」を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<functional>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<functional>](../standard-library/functional.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)



