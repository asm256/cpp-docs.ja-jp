---
title: "コンパイラ エラー C2530 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2530
dev_langs:
- C++
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7a5d6831c293f6ef25eb53cdfb6216f8142908d2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2530"></a>コンパイラ エラー C2530
'identifier': 参照を初期化する必要があります  
  
 既に宣言されていない場合、宣言されているときに、参照を初期化する必要があります。  
  
-   キーワードを使用して[extern](../../cpp/using-extern-to-specify-linkage.md)します。  
  
-   クラス、構造体または共用体のメンバーとして (および、コンス トラクターで初期化されます)。  
  
-   関数宣言または定義でのパラメーターです。  
  
-   関数の戻り値の型。  
  
 次の例では、c2530 エラーが生成されます。  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```