---
title: "CAtlFileMapping クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs: C++
helpviewer_keywords: CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a028c2458b0a5085a1f46bf31f377e6ed9e4d346
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping クラス
このクラスのメソッドへのキャスト演算子の追加メモリ マップト ファイルを表します[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 キャスト演算子で使用されるデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|により、暗黙の変換の`CAtlFileMapping`オブジェクトを`T`  **\***です。|  
  
## <a name="remarks"></a>コメント  
 このクラスの暗黙的な変換を許可する 1 つのキャスト演算子を追加する`CAtlFileMapping`オブジェクトを`T`  **\***です。 他のメンバーが、基本クラスによって提供される[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
##  <a name="operator_t_star"></a>CAtlFileMapping::operator T *  
 により、暗黙の変換の`CAtlFileMapping`オブジェクトを`T`  **\***です。  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します、 `T`  **\*** メモリ マップト ファイルの先頭へのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata)として返されたポインターとして再解釈し、 `T`  **\*** 場所*T*は、テンプレートとして使用される型です。このクラスのパラメーターです。  
  
## <a name="see-also"></a>関連項目  
 [CAtlFileMappingBase クラス](../../atl/reference/catlfilemappingbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)
