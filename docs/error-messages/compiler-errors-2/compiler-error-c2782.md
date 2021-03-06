---
title: "コンパイラ エラー C2782 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2782
dev_langs:
- C++
helpviewer_keywords:
- C2782
ms.assetid: 8b685422-294d-4f64-9f3d-c14eaf03a93d
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 125092771675363eb896d3524b8e093493f9719b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2782"></a>コンパイラ エラー C2782
'declaration': テンプレート パラメーター 'identifier' があいまいです  
  
 コンパイラは、テンプレート引数の型を特定できません。  
  
 次の例では、C2782 が生成されます。  
  
```  
// C2782.cpp  
template<typename T>  
void f(T, T) {}  
  
int main() {  
   f(1, 'c');   // C2782  
   // try the following line instead  
   // f<int>(1, 'c');  
}  
```  
  
 C2782 は、ジェネリックを使用するときにも発生することができます。  
  
```  
// C2782b.cpp  
// compile with: /clr  
generic<typename T> void gf(T, T) { }  
  
int main() {  
   gf(1, 'c'); // C2782  
   // try the following line instead  
   // gf<int>(1, 'c');  
}  
```
