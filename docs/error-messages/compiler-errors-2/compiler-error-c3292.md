---
title: "コンパイラ エラー C3292 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3292
dev_langs: C++
helpviewer_keywords: C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b5bad02a4c7eae9a30855596ccb1695430c4f15e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3292"></a>コンパイラ エラー C3292
cli 名前空間はを再度開くことはできません  
  
 コード内で cli 名前空間を宣言することはできません。  詳細については、次を参照してください。[プラットフォーム、既定値、および cli 名前空間](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では C3292 が生成されます。  
  
```  
// C3292.cpp  
// compile with: /clr /c  
namespace cli {};   // C3292  
```