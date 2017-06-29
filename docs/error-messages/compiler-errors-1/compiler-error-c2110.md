---
title: "コンパイラ エラー C2110 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2110
dev_langs:
- C++
helpviewer_keywords:
- C2110
ms.assetid: 48fd76ed-90d6-4a60-9c7b-f6ce9355b4ca
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 84b1a1930dca3759baa71552d0cfdbae3cf74070
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2110"></a>コンパイラ エラー C2110
'+': ポインターにポインターを加えようとしました  
  
 プラス ( `+` ) 演算子を使用して 2 つのポインター値を追加しようとしました。  
  
 次の例では C2110 が生成されます。  
  
```  
// C2110.cpp  
int main() {  
   int a = 0;  
   int *pa;  
   int *pb;  
   a = pa + pb;   // C2110  
}  
```