---
title: "コンパイラ エラー C3670 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3670"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3670"
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C3670
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'オーバーライド' : アクセスできない基本クラス メソッド 'メソッド' をオーバーライドできません  
  
 オーバーライドは、派生型で利用できるアクセス レベルが設定された関数だけで発生します。  詳細については、「[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)」を参照してください。  
  
 次の例では警告 C3670 が生成されます。  
  
```  
// C3670.cpp  
// compile with: /clr /c  
public ref class C {  
// Uncomment the following line to resolve.  
// public:  
   virtual void g() { }  
};  
  
public ref class D : public C {  
public:  
   virtual void f() new sealed = C::g {};   // C3670  
};  
```