---
title: "identity 構造体 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: utility/std::identity
dev_langs: C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 280ce6a24e1de9d0e7206e7f9e5b0d896d8c6787
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="identity-structure"></a>identity 構造体
テンプレート パラメーターの型定義を指定する構造体。  
  
## <a name="syntax"></a>構文  
```  
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };  
```  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`left`|指定する値。|  
  
## <a name="remarks"></a>コメント  
 このクラスにはパブリック型の定義 `type` が含まれています。これは、テンプレート パラメーターの型と同じです。 必要な型が関数パラメーターに設定されるようにするには、テンプレート関数 [forward](../standard-library/utility-functions.md#forward) と組み合わせて使用します。  
  
 このクラスは、以前のコードとの互換性を保つために、引数 `left` を返すidentity 関数 `operator()` も定義します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<utility>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>関連項目  
 [\<utility>](../standard-library/utility.md)



