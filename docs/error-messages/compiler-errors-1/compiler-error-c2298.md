---
title: "コンパイラ エラー C2298 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2298
dev_langs: C++
helpviewer_keywords: C2298
ms.assetid: eb0120ad-c850-4bdd-911d-0361229cc859
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3bd426fb1351577a1cfc42c78daa77826705341f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2298"></a>コンパイラ エラー C2298
'operation': メンバー関数の式へのポインターに無効な操作  
  
 メンバー関数の式へのポインターは、このメンバー関数を呼び出す必要があります。  
  
## <a name="example"></a>例  
 次の例では、C2298 を生成します。  
  
```  
// C2298.cpp  
#include <stdio.h>  
  
struct X {  
   void mf() {  
      puts("in X::mf");  
   }  
  
   void mf2() {  
      puts("in X::mf2");  
   }  
};  
  
X x;  
// pointer to member functions with no params and void return in X  
typedef void (X::*pmf_t)();   
  
// a pointer to member function X::mf  
void (X::*pmf)() = &X::mf;  
  
int main() {  
   int (*pf)();  
   pf = x.*pmf;   // C2298  
   +(x.*pmf);     // C2298  
  
   pmf_t pf2 = &X::mf2;  
   (x.*pf2)();   // uses X::mf2  
   (x.*pmf)();   // uses X::mf  
}  
```  
  
## <a name="example"></a>例  
 次の例では、C2298 を生成します。  
  
```  
// C2298_b.cpp  
// compile with: /c  
void F() {}  
  
class Measure {  
public:  
   void SetTrackingFunction(void (Measure::*fnc)()) {  
      TrackingFunction = this->*fnc;   // C2298  
      TrackingFunction = fnc;   // OK  
      GlobalTracker = F;   // OK  
   }  
private:  
   void (Measure::*TrackingFunction)(void);  
   void (*GlobalTracker)(void);  
};  
```