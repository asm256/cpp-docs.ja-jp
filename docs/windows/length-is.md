---
title: "length_is |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.length_is
dev_langs: C++
helpviewer_keywords: length_is attribute
ms.assetid: 1d99b883-84bb-4b1e-b098-eb780fc94f40
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6051502e81593bdb13f32d7904f912cc6f294cef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="lengthis"></a>length_is
転送する配列要素の数を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ length_is(  
   "expression"  
) ]  
```  
  
#### <a name="parameters"></a>パラメーター  
 *式*  
 1 つ以上の C 言語の式。 空の引数スロットを指定します。  
  
## <a name="remarks"></a>コメント  
 **Length_is** C++ 属性と同じ機能を持つ、 [length_is](http://msdn.microsoft.com/library/windows/desktop/aa367068) MIDL 属性。  
  
## <a name="example"></a>例  
 参照してください[first_is](../windows/first-is.md)配列のセクションを指定する方法の例についてはします。  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|フィールドに`struct`または**共用体**パラメーターをインターフェイスでは、インターフェイス メソッド|  
|**反復可能**|いいえ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [パラメーター属性](../windows/parameter-attributes.md)   
 [first_is](../windows/first-is.md)   
 [max_is](../windows/max-is.md)   
 [last_is](../windows/last-is.md)   
 [size_is](../windows/size-is.md)   
