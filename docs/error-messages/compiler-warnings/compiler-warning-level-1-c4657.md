---
title: "コンパイラの警告 (レベル 1) C4657 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4657
dev_langs:
- C++
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
caps.latest.revision: 7
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
ms.sourcegitcommit: 6cad5222fb0d97594d5b13b5cf8903eb2934ee88
ms.openlocfilehash: 2ac407b6e2ed17eb7a9c1f1232756e9977ed7511
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4657"></a>コンパイラの警告 (レベル 1) C4657
前回のビルド以降新規に追加されたデータ型が数式に含まれています  
  
 前回成功したビルド以降に、データ型が追加されたか既存のデータ型が変更されました。これは、今までソース コードに含まれていなかったデータ型です。 エディット コンティニュは、既存のデータ型への変更をサポートしません。  
  
 この警告は後に必ず[致命的なエラー C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)します。 詳細については、次を参照してください。、[サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)します。  
  
### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>現在のデバッグ セッションを終了せずにこの警告を削除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **[デバッグ]** メニューの **[コード変更を適用]**をクリックします。  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには  
  
1.  **[デバッグ]** メニューの **[デバッグの停止]**をクリックします。  
  
2.  **[ビルド]** メニューの **[ビルド]**をクリックします。
