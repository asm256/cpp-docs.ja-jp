---
title: "コンパイラ エラー C2201 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2201
dev_langs: C++
helpviewer_keywords: C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e68912ce5468f07bf18fb953adc996b755500aca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2201"></a>コンパイラ エラー C2201
'identifier': エクスポート/インポートするために外部リンケージを持つ必要があります  
  
 エクスポートされた識別子が`static`です。  
  
 次の例では C2286 が生成されます。  
  
```  
// C2201.cpp  
// compile with: /c  
__declspec(dllexport) static void func() {}   // C2201 func() is static  
__declspec(dllexport) void func2() {}   // OK  
```  
  
## <a name="see-also"></a>関連項目  
 [リンケージの種類](../../cpp/types-of-linkage.md)