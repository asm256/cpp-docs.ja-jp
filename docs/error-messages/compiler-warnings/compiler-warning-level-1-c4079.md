---
title: "コンパイラの警告 (レベル 1) C4079 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4079
dev_langs:
- C++
helpviewer_keywords:
- C4079
ms.assetid: 549759f0-e168-47e9-8c9a-de93ac843689
caps.latest.revision: 6
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
ms.openlocfilehash: 7c9cbc47fb4093d737f6c02f213c168b444cfac1
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4079"></a>コンパイラの警告 (レベル 1) C4079
不要なトークン 'token' が見つかりました  
  
 予期しないセパレーター トークンは、プラグマの引数リスト内で発生します。 プラグマの残りの部分は無視されました。  
  
 次の例では、C4079 が生成されます。  
  
```  
// C4079.cpp  
// compile with: /W1  
#pragma warning(disable : 4081)  
#pragma pack(c,16)   // C4079  
  
int main() {  
}  
```