---
title: "コンパイラ エラー C2935 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2935
dev_langs:
- C++
helpviewer_keywords:
- C2935
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d270ed23d9bddc9ef14d1ebd9a6aca78f24d59f3
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2935"></a>コンパイラ エラー C2935
'class': type-class-id がグローバル関数として再定義されています  
  
 ジェネリック クラスまたはテンプレート クラスをグローバル関数として使用することはできません。  
  
 このエラーは、中かっこが正しく一致していない場合に発生することがあります。  
  
 次の例では C2935 が生成されます。  
  
```  
// C2935.cpp  
// compile with: /c  
template<class T>  
struct TC {};   
void TC<int>() {}   // C2935  
  
// OK  
struct TC2 {};   
void TC2() {}  
```  
  
 C2935 は、ジェネリックを使用しているときも発生します。  
  
```  
// C2935b.cpp  
// compile with: /clr /c  
generic<class T>   
ref struct GC { };  
void GC<int>() {}   // C2935  
void GC() {}   // OK  
```
