---
title: "コンパイラの警告 (レベル 4) C4234 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4234"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4234"
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラの警告 (レベル 4) C4234
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非標準の拡張機能が使用されています : 'keyword' キーワードは将来の拡張のために予約されています。  
  
 使用したキーワードは、まだコンパイラに実装されていません。  
  
 この警告は、自動的にエラーになります。  この動作を変更する場合は、[warning](../../preprocessor/warning.md) を使用します。  たとえば、C4234 でレベル 4 の警告を発行させるには、  
  
```  
#pragma warning(2:4234)  
```  
  
 をソース コード ファイルに追加します。