---
title: "Cdbpropidset::setguid |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropIDSet.SetGUID
- ATL::CDBPropIDSet::SetGUID
- SetGUID
- ATL.CDBPropIDSet.SetGUID
- CDBPropIDSet::SetGUID
dev_langs: C++
helpviewer_keywords: SetGUID method
ms.assetid: 8dd0f3bf-1490-4d53-9063-322b8d821bbe
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d91cc0374474a38bd2caba66ab98003852195f9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="cdbpropidsetsetguid"></a>CDBPropIDSet::SetGUID
GUID フィールドを設定、**コンス トラクターは**構造体。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### <a name="parameters"></a>パラメーター  
 `guid`  
 [in]設定に使用される GUID、**コンス トラクターは**のフィールド、[コンス トラクターは](https://msdn.microsoft.com/en-us/library/ms717981.aspx)構造体。  
  
## <a name="remarks"></a>コメント  
 このフィールドを設定することができます、[コンス トラクター](../../data/oledb/cdbpropidset-cdbpropidset.md)もします。 このクラスの既定のコンス トラクターを使用する場合は、この関数を呼び出します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [CDBPropIDSet クラス](../../data/oledb/cdbpropidset-class.md)