---
title: "コンパイラ エラー C3043 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3043
dev_langs: C++
helpviewer_keywords: C3043
ms.assetid: 0ef55e63-e82b-48eb-9d44-690950ac34c6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2ec3f70fa176b8562067985b5b2d48ee2aa39b8e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3043"></a>コンパイラ エラー C3043
OpenMP 'critical' ディレクティブを 'critical' ディレクティブの中で、同じ名前で入れ子にすることはできません  
  
 [critical](../../parallel/openmp/reference/critical.md) ディレクティブは、同じ名前を使用する `critical` ディレクティブに入れ子にすることはできません。  
  
 次の例では C3043 が生成されます。  
  
```  
// C3043.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n1 = 1, n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp critical(MyTest)  
      {  
         ++n2;  
  
         #pragma omp critical(MyTest)   // C3043  
         // try the following line instead  
         // #pragma omp critical(MyTest2)  
         {  
            ++n3;  
         }  
      }  
   }  
}  
```