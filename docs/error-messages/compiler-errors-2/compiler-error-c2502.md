---
title: "コンパイラ エラー C2502 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2502
dev_langs:
- C++
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 396ec843c03843b506174308a5b548f50379c06f
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2502"></a>コンパイラ エラー C2502
'identifier': 基底クラスに多すぎる、アクセス修飾子  
  
 基本クラスには、1 つ以上のアクセス修飾子があります。 1 つだけアクセス修飾子 (`public`、 `private`、または`protected`) は許可されています。  
  
 次の例では、C2502 が生成されます。  
  
```  
// C2502.cpp  
// compile with: /c  
class A { };  
class B { };  
class C : private public A { };   // C2502  
  
// OK  
class D : private A {};  
class E : public A, private B {};  
```
