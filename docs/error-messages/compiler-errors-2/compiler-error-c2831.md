---
title: "コンパイラ エラー C2831 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2831
dev_langs:
- C++
helpviewer_keywords:
- C2831
ms.assetid: c8c04288-0889-4265-a077-17f94cbcdcc9
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 93eaffe8f94f7d0b5606f403a7f4fbd27560240b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2831"></a>コンパイラ エラー C2831
'operator 演算子' は、既定のパラメーターを持つことはできません。  
  
 3 つだけの演算子は、既定のパラメーターを持つことができます。  
  
-   [new](../../cpp/new-operator-cpp.md)  
  
-   割り当て =  
  
-   左かっこ (  
  
 次の例では、C2831 が生成されます。  
  
```  
// C2831.cpp  
// compile with: /c  
#define BINOP <=  
class A {  
public:  
   int i;  
   int operator BINOP(int x = 1) {   // C2831  
   // try the following line instead  
   // int operator BINOP(int x) {  
      return i+x;  
   }  
};  
```
