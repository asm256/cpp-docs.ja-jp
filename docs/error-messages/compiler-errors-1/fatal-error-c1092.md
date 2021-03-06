---
title: "致命的なエラー C1092 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fac0a5218e1faf16d3db459567c36775acd9bb12
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1092"></a>致命的なエラー C1092
エディット コンティニュはデータ型への変更をサポートしません。ビルドが必要です。  
  
 前回成功したビルド以降、データ型を追加または変更します。  
  
-   エディット コンティニュは、クラス、構造体、または列挙型の定義を含む既存のデータ型への変更をサポートしていません。 デバッグを停止し、アプリケーションをビルドする必要があります。  
  
-   エディット コンティニュが場合 vc などのプログラム データベース ファイルの新しいデータ型の追加をサポートしていません*x*0 pdb (ここで*x*メジャー バージョンの Visual C の使用) は読み取り専用です。 データ型を追加するには、コンパイラは、書き込みモードで .pdb ファイルを開く必要があります。  
  
### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>現在のデバッグ セッションを終了せずにこのエラーを削除するには  
  
1.  データ型をエラーが起こる前の状態に戻します。  
  
2.  **[デバッグ]** メニューの **[コード変更を適用]**をクリックします。  
  
### <a name="to-remove-this-error-without-changing-your-source-code"></a>ソース コードを変更せずにこのエラーを削除するには  
  
1.  **[デバッグ]** メニューの **[デバッグの停止]**をクリックします。  
  
2.  **[ビルド]** メニューの **[ビルド]**をクリックします。  
  
 詳細については、「 [サポートされているコード変更](/visualstudio/debugger/supported-code-changes-cpp)」を参照してください。
