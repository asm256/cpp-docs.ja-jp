---
title: "コンパイラ エラー C2734 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2734
dev_langs: C++
helpviewer_keywords: C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75b82a9c892ecda312b13f1adc2925a9695b4db5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2734"></a>コンパイラ エラー C2734
'identifier': const オブジェクトは、extern いない場合、初期化する必要があります  
  
 識別子が宣言されている`const`初期化されていませんが、または`extern`です。  
  
 次の例では、C2734 が生成されます。  
  
```  
// C2734.cpp  
const int j;   // C2734  
extern const int i;   // OK, declared as extern  
```