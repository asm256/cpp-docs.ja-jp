---
title: "コンパイラ エラー C2863 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2863
dev_langs:
- C++
helpviewer_keywords:
- C2863
ms.assetid: 32561d67-a795-486b-b3b6-4b90a1acb176
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 66f1b5ad8dc26cf09f31c8d996b1943e4a189e0b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2863"></a>コンパイラ エラー C2863
'interface': インターフェイスはフレンドを持つことはできません  
  
 インターフェイスでフレンドを宣言することはできません。  
  
 次の例では、C2863 が生成されます。  
  
```  
// C2863.cpp  
// compile with: /c  
#include <unknwn.h>  
  
class CMyClass {  
   void *f();  
};   
  
__interface IMyInterface {  
   void g();  
  
   friend int h();   // 2863  
   friend interface IMyInterface1;  // C2863  
   friend void *CMyClass::f();  // C2863  
};  
```
