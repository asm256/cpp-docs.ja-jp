---
title: "コンパイラ エラー C3890 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3890"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3890"
ms.assetid: 2f22c2fd-c14e-45e1-b936-b739ffc0b135
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# コンパイラ エラー C3890
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : リテラル データ メンバーのアドレスを指定することはできません  
  
 ガベージ コレクション ヒープにリテラル データ メンバーがあります。ガベージ コレクション ヒープのオブジェクトは移動可能なため、アドレスを指定できません。  
  
 次の例では警告 C3890 が生成されます。  
  
```  
// C3890.cpp  
// compile with: /clr  
ref struct Y1 {  
   literal int staticConst = 9;  
};  
  
int main() {  
   int p = &Y1::staticConst;   // C3890  
   int p2 = Y1::staticConst;   // OK  
}  
```