---
title: "CComHeapPtr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
dev_langs: C++
helpviewer_keywords: CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d851e2c6fb4892bd65cf26ea747a6b99a8006cee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ccomheapptr-class"></a>CComHeapPtr クラス
ヒープのポインターを管理するためのスマート ポインター クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T>  
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ヒープに格納されるオブジェクトの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|コンストラクターです。|  
  
## <a name="remarks"></a>コメント  
 `CComHeapPtr`派生した`CHeapPtr`が使用して[CComAllocator](../../atl/reference/ccomallocator-class.md) COM ルーチンを使用するメモリを割り当てられません。 参照してください[CHeapPtr](../../atl/reference/cheapptr-class.md)と[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)メソッドで使用できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md)  
  
 `CComHeapPtr`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="ccomheapptr"></a>CComHeapPtr::CComHeapPtr  
 コンストラクターです。  
  
```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 既存の `CComHeapPtr` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 既存を使用して、ヒープのポインターを作成することができます必要に応じて`CComHeapPtr`オブジェクト。 場合は、新しい`CComHeapPtr`オブジェクトは、新しいポインターとリソースを管理する責任を引き継ぎます。  
  
## <a name="see-also"></a>関連項目  
 [CHeapPtr クラス](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrBase クラス](../../atl/reference/cheapptrbase-class.md)   
 [CComAllocator クラス](../../atl/reference/ccomallocator-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
