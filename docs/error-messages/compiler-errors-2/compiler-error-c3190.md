---
title: "コンパイラ エラー C3190 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3190
dev_langs: C++
helpviewer_keywords: C3190
ms.assetid: 7c701afa-85a7-4f7a-8881-0662436ac244
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 29d85c8a58b20c5a3c4492c56a66591e1509f2c4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3190"></a>コンパイラ エラー C3190
指定されたテンプレート引数のインスタンス化が 'type' のメンバー関数の明示的なインスタンス化ではありません。  
  
 コンパイラは、明示的な関数のインスタンス生成。 試行を検出しました。ただし、指定された型引数が一致しません、使用できる関数のいずれか。  
  
 次の例では、C3190 が生成されます。  
  
```  
// C3190.cpp  
// compile with: /LD  
template<class T>  
struct A {  
   A(int x = 0) {  
   }  
   A(int x, int y) {  
   }  
};  
  
template A<float>::A();   // C3190  
// try the following line instead  
// template A<int>::A(int);  
  
struct Y {  
   template<class T> void f(T);  
};  
  
template<class T> void Y::f(T) { }  
  
template void Y::f(int,int);   // C3190  
  
template<class OT> class X {  
   template<class T> void f2(T,OT);  
};  
  
template<class OT> template<class T> void X<OT>::f2(T,OT) {}  
  
template void X<float>::f2<int>(int,char);   // C3190  
// try one of the following lines instead  
// template void X<char>::f2(int, char);  
// template void X<char>::f2<int>(int,char);  
// template void X<char>::f2<>(int,char);  
```