---
title: "一次式の識別子 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: identifiers, designating objects
ms.assetid: d4602fe6-e7e6-40cc-9823-3b1ebf5d3d38
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ce62a6ad0f0cb36678de0756d77155769393f760
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="identifiers-in-primary-expressions"></a>一次式の識別子
識別子は、整数、**浮動小数点**、`enum`、`struct`、**共用体**、配列、ポインター、または関数型を持つことができます。 識別子は、オブジェクトの指定として宣言された場合 (その場合は左辺値)、または関数として宣言された場合 (その場合は関数指定子) の一次式です。 左辺値の定義については、「[左辺値と右辺値の式](../c-language/l-value-and-r-value-expressions.md)」を参照してください。  
  
 配列識別子によって表されるポインター値は変数ではないので、配列識別子は、代入演算の左オペランドを形成することができず、したがって変更可能な左辺値ではありません。  
  
 関数として宣言される識別子は、値が関数のアドレスであるポインターを表します。 ポインターは、指定された型の値を返す関数をアドレス指定します。 したがって、関数識別子は代入演算子の左辺値にすることもできません。 詳細については、[識別子](../c-language/c-identifiers.md)に関するページを参照してください。  
  
## <a name="see-also"></a>関連項目  
 [C 一次式](../c-language/c-primary-expressions.md)