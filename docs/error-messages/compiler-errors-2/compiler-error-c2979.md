---
title: "コンパイラ エラー C2979 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2979
dev_langs:
- C++
helpviewer_keywords:
- C2979
ms.assetid: 98bd9043-ec44-451e-a482-3a8e35fc7464
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 9444a5f9c894058277f3957458ecfcd242048101
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2979"></a>コンパイラ エラー C2979
明示的な特殊化はジェネリックではサポートされていません  
  
 ジェネリック クラスの宣言が正しくありません。  参照してください[ジェネリック](../../windows/generics-cpp-component-extensions.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では C2979 が生成されます。  
  
```  
// C2979.cpp  
// compile with: /clr /c  
generic <>   
ref class Utils {};   // C2979 error  
  
generic <class T>  
ref class Utils2 {};   // OK  
```
