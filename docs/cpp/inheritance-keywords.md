---
title: "継承キーワード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs: C++
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes [C++]
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes [C++], declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 65d338f642d705fec6f1a45b5e88f05c1ee55cc8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="inheritance-keywords"></a>継承キーワード
**Microsoft 固有の仕様**  
  
```  
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;  
```  
  
 ここで、  
  
 *クラス名*  
 宣言するクラスの名前。  
  
 C++ では、クラスを定義する前にクラス メンバーへのポインターを宣言できます。 例:  
  
```  
class S;  
int S::*p;  
```  
  
 上記のコードで`p`クラス %s の整数メンバーへのポインターとして宣言されました。ただし、`class S`が宣言されただけです。 このコードで定義されていません。 コンパイラがこのようなポインターを検出した場合、そのポインターの汎化表現を作成する必要があります。 この表現のサイズは、指定した継承モデルによって異なります。 コンパイラに継承モデルを指定するには 4 つの方法があります。  
  
-   下にある IDE で**メンバーへのポインター表現**  
  
-   使用して、コマンドラインで、 [/vmg](../build/reference/vmb-vmg-representation-method.md)スイッチ  
  
-   使用して、 [pointers_to_members](../preprocessor/pointers-to-members.md)プラグマ  
  
-   継承キーワード `__single_inheritance`、`__multiple_inheritance`、および `__virtual_inheritance` を使って指定する この手法により、クラス単位で継承モデルを制御します。  
  
    > [!NOTE]
    >  常にクラスを定義した後で、そのクラスのメンバーへのポインターを宣言する場合は、これらのオプションを使用する必要がありません。  
  
 クラスを定義する前に、そのクラスのメンバーへのポインターを宣言すると、作成される実行可能ファイルのサイズと速度に影響を与えます。 クラスで使用する継承が複雑になるほど、そのクラスのメンバーへのポインターを表すために必要なバイト数が多くなります。したがって、そのポインターの解釈に必要なコードも大きくなります。 単一継承は最も簡素で、仮想継承は最も複雑です。  
  
 上記の例を次のように変更します。  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 この場合、コマンド ライン オプションやプラグマに関係なく、`class S` のメンバーへのポインターは最小サイズの表現を使用します。  
  
> [!NOTE]
>  メンバーへのクラス ポインター表現の同じ前方宣言は、そのクラスのメンバーへのポインターを宣言する各翻訳単位で発生する必要があり、その宣言はメンバーへのポインターを宣言する前に発生する必要があります。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)