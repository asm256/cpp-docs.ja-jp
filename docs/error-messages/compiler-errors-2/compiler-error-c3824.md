---
title: "コンパイラ エラー C3824 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3824
dev_langs: C++
helpviewer_keywords: C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 529e881d8872d3ea1d69da14ac393282c4f3efc1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3824"></a>コンパイラ エラー C3824
'member': 関数パラメーター、戻り値の型 (静的メンバー) は、このコンテキストでこの型は指定できません  
  
 固定ポインターが、型を返す、関数パラメーターにすることはできませんまたは宣言`static`です。  
  
## <a name="example"></a>例  
 次の例では、C3824 が生成されます。  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
