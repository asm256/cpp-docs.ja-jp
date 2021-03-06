---
title: "A.21   Scoping Variables with the private Clause | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.21   Scoping Variables with the private Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の例で `i` と `j` の値は並列領域の終了に未定義です :  
  
```  
int i, j;  
i = 1;  
j = 2;  
#pragma omp parallel private(i) firstprivate(j)  
{  
  i = 3;  
  j = j + 2;  
}  
printf_s("%d %d\n", i, j);  
```  
  
 `private` 句の詳細についてはページの 25 [セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) を参照してください。