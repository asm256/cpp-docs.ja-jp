---
title: "致命的なエラー C1307 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1307
dev_langs: C++
helpviewer_keywords: C1307
ms.assetid: 6f77d3d4-ba8a-476c-b540-aff19eb4efc4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1173f538f02e8178d523bb51476b4a10427099ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1307"></a>致命的なエラー C1307
プロファイル データが集められてからプログラムが編集されました。  
  
 使用する場合[/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)リンカー/LTCG:PGINSTRUMENT 後に再コンパイルされた入力モジュールの検出、およびモジュールが、既存のプロファイル データは関連性がなくなったポイントに変更されたことです。 たとえば、再コンパイルされたモジュール内の呼び出し先が変更された場合、コンパイラは C1307 に生成されます。  
  
 このエラーを解決するには、/LTCG:PGINSTRUMENT を実行、すべてのテストの実行を再実行し、/LTCG:PGOPTIMIZE を実行します。 を実行できない/LTCG:PGINSTRUMENT とすべてのテストを再実行する場合は、最適化されたイメージを作成する/LTCG:PGOPTIMIZE ではなく/LTCG:PGUPDATE を使用します。