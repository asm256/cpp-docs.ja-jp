---
title: "コンパイラ エラー C2217 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2217
dev_langs: C++
helpviewer_keywords: C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0f1795534af1332859fd1a33a137573df82643b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2217"></a>コンパイラ エラー C2217
'attribute1' が 'attribute2' が必要です。  
  
 関数の最初の属性には、2 番目の属性が必要です。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  中断 (`__interrupt`) として宣言された関数`near`です。 中断する必要があります関数`far`です。  
  
2.  宣言された関数の割り込み`__stdcall`、または`__fastcall`です。 割り込み関数呼び出し規約を C を使用する必要があります。  
  
## <a name="example"></a>例  
 C2217 は、可変個の引数を受け取る CLR 関数にデリゲートをバインドしようとする場合にも発生することができます。 関数は、e param 配列のオーバー ロードもが、代わりに使用します。 次の例では、C2217 を生成します。  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```