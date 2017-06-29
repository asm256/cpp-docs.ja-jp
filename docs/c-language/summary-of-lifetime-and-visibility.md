---
title: "有効期間と可視性の概要 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- lifetime, and visibility
- visibility, identifiers
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 25d8ed78733455b8dab0e69e70aebd140070a312
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="summary-of-lifetime-and-visibility"></a>有効期間と可視性の概要
次の表は、ほとんどの識別子について、有効期間と可視性をまとめたものです。 最初の&3; 列は、有効期間および可視性を定義する属性を示します。 最初の&3; 列によって指定された属性を持つ識別子には、4 番目および&5; 番目の列に表示される有効期間および可視性があります。 ただし、表には、使用可能なすべてのケースは示されていません。 詳細については、[ストレージ クラス](../c-language/c-storage-classes.md)に関するページを参照してください。  
  
### <a name="summary-of-lifetime-and-visibility"></a>有効期間と可視性の概要  
  
|属性: <br /><br /> レベル|アイテム|ストレージ クラス<br /><br /> 指定子|結果: <br /><br /> 有効期間|可視性|  
|---------------------------|----------|----------------------------------|--------------------------|----------------|  
|ファイル スコープ|変数定義|**static**|Global|発生元のソース ファイルの剰余残りの部分|  
||変数宣言|`extern`|Global|発生元のソース ファイルの剰余残りの部分|  
||関数プロトタイプまたは定義|**static**|Global|単一のソース ファイル|  
||関数プロトタイプ|`extern`|Global|ソース ファイルの残りの部分|  
|ブロック スコープ|変数宣言|`extern`|Global|ブロック|  
||変数定義|**static**|Global|ブロック|  
||変数定義|**auto** か **register**|ローカル|ブロック|  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 次の例は、変数のブロック、入れ子、可視性を示します。  
  
### <a name="code"></a>コード  
  
```  
// Lifetime_and_Visibility.c  
  
#include <stdio.h>  
  
int i = 1;  // i defined at external level  
  
int main()  // main function defined at external level  
{  
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)  
    {                                 // Begin first nested block  
        int i = 2, j = 3;          // i and j defined at internal level  
        printf_s( "%d %d\n", i, j );  // Prints 2, 3  
        {                             // Begin second nested block  
            int i = 0;                // i is redefined  
            printf_s( "%d %d\n", i, j ); // Prints 0, 3  
        }                             // End of second nested block  
        printf_s( "%d\n", i );        // Prints 2 (outer definition  
                                      //  restored)  
    }                                 // End of first nested block  
    printf_s( "%d\n", i );            // Prints 1 (external level  
                                      // definition restored)  
    return 0;  
}   
```  
  
### <a name="comments"></a>コメント  
 この例では、4 つの表示レベルとして、外部レベルと&3; つのブロック レベルがあります。 値は、各ステートメントに続くコメントに示すとおりに画面に出力されます。  
  
## <a name="see-also"></a>関連項目  
 [有効期間、スコープ、可視性、およびリンケージ](../c-language/lifetime-scope-visibility-and-linkage.md)