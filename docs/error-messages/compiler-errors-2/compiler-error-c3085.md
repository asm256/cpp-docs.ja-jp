---
title: "コンパイラ エラー C3085 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3085
dev_langs:
- C++
helpviewer_keywords:
- C3085
ms.assetid: 1ac40bf2-f63e-439e-8921-47e6dadc8354
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3d528d56a08cf6333e671ba6db18bbbe7a1be932
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3085"></a>コンパイラ エラー C3085
'constructor': コンストラクターを 'keyword' にすることはできません  
  
 コンストラクターが正しく宣言されていません。 詳細については、「 [Override Specifiers](../../windows/override-specifiers-cpp-component-extensions.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では C3085 が生成されます。  
  
```  
// C3085.cpp  
// compile with: /c /clr  
ref struct S {  
   S() abstract;   // C3085  
   S(S%) abstract;   // C3085  
};  
  
ref struct T {  
   T() sealed {}   // C3085  
   T(T%) sealed {}   // C3085  
};  
```
