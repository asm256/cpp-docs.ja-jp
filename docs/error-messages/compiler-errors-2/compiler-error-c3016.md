---
title: "コンパイラ エラー C3016 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3016
dev_langs:
- C++
helpviewer_keywords:
- C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b2c0ee841f74294957a3fa5aae40f8d99d78748b
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3016"></a>コンパイラ エラー C3016
'var': OpenMP 'for' ステートメントのインデックス変数は、符号付きの整数型を含んでいなければなりません  
  
 OpenMP `for` ステートメントのインデックス変数は、符号付きの整数型である必要があります。  
  
 次の例では C3016 が生成されます。  
  
```  
// C3016.cpp  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel  
   {  
      unsigned int i = 0;  
      // Try the following line instead:  
      // int i = 0;  
  
      #pragma omp for  
      for (i = 0; i <= 10; ++i)   // C3016  
      {  
      }  
   }  
}  
```
