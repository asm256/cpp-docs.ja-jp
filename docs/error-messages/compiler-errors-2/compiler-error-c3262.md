---
title: "コンパイラ エラー C3262 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3262
dev_langs: C++
helpviewer_keywords: C3262
ms.assetid: 3e74b9aa-de3c-4492-9331-ee73012b958b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5fb6a0bd41b2c81b011cf8762cecedad9c5e7ebd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3262"></a>コンパイラ エラー C3262
無効な配列のインデックスです。'#' 次元が指定されました。'#' 次元の 'array type' が選択されています。  
  
配列の添字が正しくありません。 インデックスの数が配列の次元数と一致しない可能性があります。  
  
次の例では C3262 が生成されます。  
  
```  
// C3262.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
using namespace System;  
  
#define ARRAY_SIZE 2  
  
ref class MyClass {  
public:  
   int m_i;  
};  
  
// returns a multidimensional managed array of a reference type  
array<MyClass^, 2>^ Test0() {  
   int i, j;  
   array< MyClass^, 2 >^ local = new array< MyClass^, 2 >  
      (ARRAY_SIZE, ARRAY_SIZE);  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++)  
      for (j = 0 ; j < ARRAY_SIZE ; j++) {  
         local[i][j] = new MyClass;   // C3262  
         // try the following line instead  
         // local[i,j] = new MyClass;     
         local[i,j] -> m_i = i;  
      }  
  
      return local;  
}  
  
int main() {     
   int i, j;  
  
   array< MyClass^, 2 >^ MyClass0;  
   MyClass0 = Test0();  
}  
```  
