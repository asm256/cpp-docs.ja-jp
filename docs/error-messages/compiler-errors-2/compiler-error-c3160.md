---
title: "コンパイラ エラー C3160 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3160
dev_langs:
- C++
helpviewer_keywords:
- C3160
ms.assetid: a250c433-8adf-43b9-8dee-c3794e09b0a5
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: df09956b70d88b2ebb9efa542aad898f3d1295f2
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3160"></a>コンパイラ エラー C3160
'pointer': マネージ クラスまたは WinRT クラスのデータ メンバーにはこの型を指定できません。  
  
 内部のガベージ コレクション ポインターは、マネージ クラスまたは WinRT クラスの内部を指す場合があります。 オブジェクト全体のポインターよりも遅く、ガベージ コレクターによる特別な処理を必要とするため、クラスのメンバーとして内部のマネージ ポインターを宣言することはできません。  
  
 次の例では C3160 が生成されます。  
  
```  
// C3160.cpp  
// compile with: /clr  
ref struct A {  
   // cannot create interior pointers inside a class  
   interior_ptr<int> pg;   // C3160  
   int g;   // OK  
   int* pg2;   // OK  
};  
  
int main() {  
   interior_ptr<int> pg2;   // OK  
}  
```  

