---
title: "コンパイラ エラー C2193 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2193
dev_langs: C++
helpviewer_keywords: C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e59b7e3ab659ee7760254680e51db9e2d4ca35d7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2193"></a>コンパイラ エラー C2193
'identifier': セグメント内の既存の  
  
 関数を使用して 2 つの異なるセグメントに格納された`alloc_text`と`code_seg`プラグマ。  
  
 次の例では、C2193 が生成されます。  
  
```  
// C2193.cpp  
// compile with: /c  
extern "C" void MYFUNCTION();  
#pragma alloc_text(MYCODE, MYFUNCTION)  
#pragma code_seg("MYCODE2")  
extern "C" void MYFUNCTION() {}   // C2193  
extern "C" void MYFUNCTION2() {}  
```