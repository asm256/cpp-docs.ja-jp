---
title: "コンパイラ エラー C2671 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2671
dev_langs: C++
helpviewer_keywords: C2671
ms.assetid: fc0ee40f-c8f3-408f-b89d-745d149c4169
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4cfea4daeb6bb4adce028cfee19bb33b8e1a008d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2671"></a>コンパイラ エラー C2671
'function': 静的メンバー関数には、'this' ポインターはありません。  
  
 A`static`メンバー関数にアクセスしようとしました。`this`です。  
  
 次の例では、C2671 が生成されます。  
  
```  
// C2671.cpp  
struct S {  
   static S* const func() { return this; }  // C2671  
};  
```