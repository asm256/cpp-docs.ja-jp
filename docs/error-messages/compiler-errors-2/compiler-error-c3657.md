---
title: "コンパイラ エラー C3657 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3657
dev_langs: C++
helpviewer_keywords: C3657
ms.assetid: 89a28a18-4c17-43a1-bda6-deb52c32d203
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2fec7db6488194ac80af45fa3cc37fb9a2bf1a8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3657"></a>コンパイラ エラー C3657
デストラクターが明示的にオーバーライドできませんまたは明示的にオーバーライドできます。  
  
 デストラクターまたはファイナライザーは、明示的にオーバーライドすることはできません。 詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)です。  
  
## <a name="example"></a>例  
 次の例では、C3657 を生成します。  
  
```  
// C3657.cpp  
// compile with: /clr  
public ref struct I {  
   virtual ~I() { }  
   virtual void a();  
};  
  
public ref struct D : I {  
   virtual ~D() = I::~I {}   // C3657  
   virtual void a() = I::a {}   // OK  
};  
```