---
title: "コンパイラ エラー C3394 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3394
dev_langs: C++
helpviewer_keywords: C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 69a4f9ebd8df95a5a65191b19d4d130eb6ede196
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3394"></a>コンパイラ エラー C3394
制約句の構文エラー: 'identifier' が見つかりましたが、型を指定しなければなりません  
  
 制約の形式が間違っています。  詳細については、次を参照してください。[ジェネリック型パラメーターの制約 (C + + CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では C3394 が生成されます。  
  
```  
// C3394.cpp  
// compile with: /clr /c  
ref class MyClass {};  
ref class R {  
   generic<typename T>  
   where T : static   // C3394  
   // try the following line instead  
   // where T : MyClass  
   void f() {}  
};  
```