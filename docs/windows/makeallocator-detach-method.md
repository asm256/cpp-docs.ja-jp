---
title: "Makeallocator::detach メソッド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAllocator::Detach
dev_langs: C++
helpviewer_keywords: Detach method
ms.assetid: 78012634-2dda-4ea2-9ffe-40f105d2fe47
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dabfbbc205e340b74498f422e2802f481c23275
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="makeallocatordetach-method"></a>MakeAllocator::Detach メソッド
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
__forceinline void Detach();  
```  
  
## <a name="remarks"></a>コメント  
 によって割り当てられたメモリの関連付けを解除、 [Allocate](../windows/makeallocator-allocate-method.md) MakeAllocator、現在のメソッドです。  
  
 Detach() を呼び出すと、した割り当てメソッドによって提供されるメモリを削除する必要があります。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [MakeAllocator クラス](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)