---
title: "コンパイラ エラー C3743 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3743
dev_langs: C++
helpviewer_keywords: C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71e35535a7e6c9916c6dd6ac563cfd5bdf76fbce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3743"></a>コンパイラ エラー C3743
できますのみフック/アンフック インターフェイス全体 event_receiver の 'layout_dependent' パラメーターが true の場合  
  
 [_ _Unhook](../../cpp/unhook.md)関数に渡された値に基づいて引き継ぎパラメーターの数によって異なります、`layout_dependent`内のパラメーター、 [event_receiver](../../windows/event-receiver.md)クラスです。  
  
 次の例では、C3743 が生成されます。  
  
```  
// C3743.cpp  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
[module(name="xx")];  
[object] __interface I { HRESULT f(); };  
  
[event_receiver(com, layout_dependent=true), coclass]  
struct R : I {  
        HRESULT f() {  
      return 0;  
   }  
        R() {  
   }  
  
   R(I* a) {  
      __hook(I, a, &R::f);   // C3743  
      // The following line resolves the error.  
      // __hook(I, a);  
   }  
};  
```