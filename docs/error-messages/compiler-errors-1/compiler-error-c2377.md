---
title: "コンパイラ エラー C2377 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2377
dev_langs: C++
helpviewer_keywords: C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: df5596f92c0205a45f3ef03e2ffba212bf168c30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2377"></a>コンパイラ エラー C2377
'identifier': 再定義されています。typedef は他のどのシンボルでもオーバーロードできません  
  
 `typedef` 識別子が再定義されます。  
  
 次の例では C2377 が生成されます。  
  
```  
// C2377.cpp  
// compile with: /c  
typedef int i;  
int i;   // C2377  
int j;   // OK  
```