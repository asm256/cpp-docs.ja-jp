---
title: "2.7.2.4 shared | Microsoft Docs"
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
ms.assetid: c9c5d653-58fc-4620-ab0a-443ac4f8ba2e
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.4 shared
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

この句によってチームのすべてのスレッド間の  *可変リスト*  に表示される変数を共有します。  チーム内のスレッドはすべて  **共有**  の変数に対して同じストレージ領域にアクセスします。  
  
 **共有**  句の構文は次のとおりです。:  
  
```  
shared(variable-list)  
```