---
title: "コンパイラ エラー C3624 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3624
dev_langs:
- C++
helpviewer_keywords:
- C3624
ms.assetid: eaac6a4f-eb11-4e4d-ab12-124ba995c5cf
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8ce571a05b801361f8e0a5f21c9dba1c159bbf88
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3624"></a>コンパイラ エラー C3624
'type': この型の使用には、アセンブリ 'assembly' への参照が必要です  
  
 コードのコンパイルに必要なアセンブリ (参照) が指定されていません。アセンブリを渡して、 [#using](../../preprocessor/hash-using-directive-cpp.md)ディレクティブです。  
  
## <a name="example"></a>例  
次の例では、C3624 が生成されます。  
  
```  
// C3624.cpp  
// compile with: /clr /c  
#using <System.Windows.Forms.dll>  
  
// Uncomment the following 2 lines to resolve.  
// #using <System.dll>  
// #using <System.Drawing.dll>  
  
using namespace System;  
  
public ref class MyForm : public Windows::Forms::Form {};   // C3624  
```  

