---
title: "コンパイラ エラー C2751 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2751
dev_langs: C++
helpviewer_keywords: C2751
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e6865276b3ca43db309e474f671a8423d3c307e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2751"></a>コンパイラ エラー C2751
'parameter': 関数パラメーターの名前を修飾することはできません  
  
 関数のパラメーターとして、修飾名を使用することはできません。  
  
 次の例では、C2751 が生成されます。  
  
```  
// C2751.cpp  
namespace std {  
   template<typename T>  
   class list {};  
}  
  
#define list std::list  
void f(int &list){}   // C2751  
```