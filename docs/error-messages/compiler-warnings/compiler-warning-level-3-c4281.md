---
title: "コンパイラの警告 (レベル 3) C4281 |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4281
dev_langs:
- C++
helpviewer_keywords:
- C4281
ms.assetid: a9771261-5725-4fc6-87b6-16cf92113a25
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: cfe21418e4f5fdbdfb82c79c7cd50a1d3fa0a97e
ms.contentlocale: ja-jp
ms.lasthandoff: 04/01/2017

---
# <a name="compiler-warning-level-3-c4281"></a>コンパイラの警告 (レベル 3) C4281
型 'type' から '-> operator' の再帰が発生しました  
  
 コードにより**-> 演算子**自体を呼び出す。  
  
 次の例では、C4281 が生成されます。  
  
```  
// C4281.cpp  
// compile with: /W3 /WX  
struct A;  
struct B;  
struct C;  
  
struct A  
{  
   int z;  
   B& operator->();  
};  
  
struct B  
{  
   C& operator->();  
};  
  
struct C  
{  
   A& operator->();  
};  
  
void f(A p)  
{  
   int i = p->z; // C4281  
}  
```
