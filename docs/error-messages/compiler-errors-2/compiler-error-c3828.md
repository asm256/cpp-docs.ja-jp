---
title: "コンパイラ エラー C3828 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3828
dev_langs:
- C++
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1b2dfaa6e0c414c80122bcb4291bb021bc1f3c74
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3828"></a>コンパイラ エラー C3828
'object type': クラスまたは WinRTclasses 仮引数のマネージ インスタンスの作成中に許可されていません  
  
 マネージ型または Windows ランタイム型のオブジェクトを作成する場合は、演算子の配置形式を使用することはできません[ref new、gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md)または[新しい](../../cpp/new-operator-cpp.md)です。  
  
 次の例では、C3828 を生成し、その修正方法を示しています。  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```
