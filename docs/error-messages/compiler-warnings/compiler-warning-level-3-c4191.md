---
title: "コンパイラの警告 (レベル 3) C4191 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4191
dev_langs:
- C++
helpviewer_keywords:
- C4191
ms.assetid: 576d3bc6-95b7-448a-af31-5d798452df09
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 5cdd66e6318867a7f4df8ff70b6440ae6e7bfa3a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4191"></a>コンパイラの警告 (レベル 3) C4191
'operator/operation' : 'type of expression' から 'type required' への変換は保証されません  
  
 関数ポインターを使用するいくつかの操作は安全でないと見なされます。  
  
-   関数の種類の呼び出し規則が異なる場合。  
  
-   関数の種類の復帰規則が異なる場合。  
  
-   引数または戻り値の型のサイズ、型のカテゴリ、または分類が異なる場合。  
  
-   引数リストの長さが異なる場合 ( `__cdecl`では、短い方の引数リストが varargs であっても、長い方のリストから短い方へキャストされる場合のみ)。  
  
-   データへのポインター (以外の**void\***) 関数へのポインターに対してエイリアス化です。  
  
-   その他の型の違いによって、 `reinterpret_cast`でエラーまたは警告が発生する場合。  
  
 結果として得られたポインターを使用して関数を呼び出すと、プログラムがクラッシュする可能性があります。  
  
 既定では、この警告はオフに設定されています。 参照してください[コンパイラの警告無効になっている既定](../../preprocessor/compiler-warnings-that-are-off-by-default.md)詳細についてはします。  
  
 次の例では C4191 が生成されます。  
  
```  
// C4191.cpp  
// compile with: /W3 /clr  
#pragma warning(default: 4191)  
  
void __clrcall f1() { }  
void __cdecl   f2() { }  
  
typedef void (__clrcall * fnptr1)();  
typedef void (__cdecl   * fnptr2)();  
  
int main() {  
   fnptr1 fp1 = static_cast<fnptr1>(&f1);  
   fnptr2 fp2 = (fnptr2) &f2;  
  
   fnptr1 fp3 = (fnptr1) &f2;   // C4191  
   fnptr2 fp4 = (fnptr2) &f1;   // C4191  
};  
```
