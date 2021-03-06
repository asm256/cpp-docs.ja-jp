---
title: "コンパイラ エラー C2993 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2993
dev_langs:
- C++
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: a6306b2c3c632d25ee6b37a025516f759cc126a6
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2993"></a>コンパイラ エラー C2993
'identifier': 非型テンプレート パラメーター 'parameter' に対する無効な型  
  
 構造体または共用体の引数を持つテンプレートを宣言することはできません。 ポインターを使用して、テンプレート パラメーターとして構造体と共用体を渡します。  
  
 次の例では、C2993 が生成されます。  
  
```  
// C2993.cpp  
// compile with: /c  
// C2993 expected  
struct MyStruct {  
   int a;char b;  
};  
  
template <class T, struct MyStruct S>   // C2993  
  
// try the following line instead  
// template <class T, struct MyStruct * S>  
class CMyClass {};  
```  
  
 このエラーは Visual Studio .NET 2003 で行われたコンパイラ準拠作業の結果として生成することも: 浮動小数点の非型テンプレート パラメーターが許可されなくなりました。 C++ 標準は許可されません浮動小数点型の非型テンプレート パラメーター。  
  
 関数テンプレートは、使用する関数の引数を渡す浮動は非型テンプレート パラメーター (このコードが有効になります、Visual Studio .NET 2003 バージョンと Visual Studio .NET バージョンの Visual C) をポイントします。 クラス テンプレートは場合、簡単な回避策はありません。  
  
```  
// C2993b.cpp  
// compile with: /c  
template<class T, float f> void func(T) {}   // C2993  
  
// OK  
template<class T>   void func2(T, float) {}  
```
