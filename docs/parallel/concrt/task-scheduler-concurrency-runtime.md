---
title: "タスク スケジューラ (同時実行ランタイム) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- oversubscription [Concurrency Runtime]
- task scheduler [Concurrency Runtime], oversubscription
- schedule groups [Concurrency Runtime]
- task scheduler [Concurrency Runtime], lightweight tasks
- task scheduler [Concurrency Runtime]
- lightweight tasks [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler policies
- task scheduler [Concurrency Runtime], schedule groups
- wait function [Concurrency Runtime]
- task scheduler [Concurrency Runtime], scheduler instances
- scheduler instances [Concurrency Runtime]
- scheduler policies [Concurrency Runtime]
- task scheduler [Concurrency Runtime], wait function
ms.assetid: 9aba278c-e0c9-4ede-b7c6-fedf7a365d90
caps.latest.revision: "42"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 692f02f6ad2d7486c8460d3dae42500f165f60b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="task-scheduler-concurrency-runtime"></a>タスク スケジューラ (同時実行ランタイム)
ドキュメントのこの部分のトピックでは、同時実行ランタイムのタスク スケジューラの重要な機能について説明します。 タスク スケジューラは、同時実行ランタイムを使用する既存のコードのパフォーマンスを微調整するときに役立ちます。  
  
> [!IMPORTANT]
>  タスク スケジューラは、[!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] アプリから使用できません。 詳細については、次を参照してください。 [Windows ストア アプリ用 C++ で非同期操作の作成](../../parallel/concrt/creating-asynchronous-operations-in-cpp-for-windows-store-apps.md)です。  
>   
>  Visual Studio 2015 以降では、 [concurrency::task](../../parallel/concrt/reference/task-class.md)クラスおよび ppltasks.h 内の関連する型、スケジューラとして Windows ThreadPool が使用されます。 このトピックは、ppltasks.h で定義されている型には該当しなくなりました。 parallel_for などの並列アルゴリズムでは引き続き、既定のスケジューラとして同時実行ランタイムが使用されます。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 始めることをお勧めタスク スケジューラを使用してアプリケーションのパフォーマンスを微調整できますが、ため、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)場合同時実行ランタイムに新しいです。  
  
 タスク スケジューラは、実行時にタスクをスケジュールおよび調整します。 A*タスク*特定のジョブを実行する作業の単位です。 通常、タスクは、他のタスクと並列に実行できます。 タスク グループ項目、並列アルゴリズム、非同期エージェントによって実行される作業はすべて、タスクの例です。  
  
 タスク スケジューラは、複数のコンピューティング リソースを持つコンピューター上での効率的なタスクのスケジュール設定に関連する詳細を管理します。 また、タスク スケジューラでは、基になるオペレーティング システムの最新機能も使用されます。 そのため、同時実行ランタイムを使用するアプリケーションは、機能を拡張したハードウェア上で自動的に拡張され、向上します。  
  
 [その他の同時実行モデルとの比較](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)プリエンプティブ メカニズムと協調スケジュール メカニズムの違いについて説明します。 タスク スケジューラは、処理リソースを最大限活用するために、協調スケジュールとワーク スティーリング アルゴリズムを、オペレーティング システムのプリエンプティブ スケジューラと共に使用します。  
  
 同時実行ランタイムには既定のスケジューラが用意されているため、インフラストラクチャの詳細を管理する必要はありません。 そのため、通常は、タスク スケジューラを直接使用しないでください。 ただし、アプリケーションの品質ニーズを満たすために、タスク スケジューラを使用して独自のスケジューリング ポリシーを提供したり、スケジューラを特定のタスクに関連付けたりすることもできます。 たとえば、4 つまでのプロセッサに対応した並列並べ替えルーチンがあるとします。 使用することができます*スケジューラ ポリシー*を 4 つ以下の同時実行タスクを生成するスケジューラを作成します。 このスケジューラで並べ替えルーチンを実行すると、アクティブな他のスケジューラで残りの処理リソースを使用できるようになります。  
  
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)|スケジューラ インスタンスと、`concurrency::Scheduler` クラスと `concurrency::CurrentScheduler` クラスを使用してスケジューラ インスタンスを使用する方法について説明します。 スケジューラ インスタンスは、明示的なスケジューリング ポリシーを特定の種類のワークロードに関連付ける場合に使用します。|  
|[スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)|スケジューラ ポリシーの役割について説明します。 スケジューラ ポリシーは、スケジューラでタスクを管理する場合に使用される方法を制御するときに使用します。|  
|[スケジュール グループ](../../parallel/concrt/schedule-groups.md)|スケジュール グループの役割について説明します。 スケジュール グループは、タスク間で高いレベルの局所性が求められる場合 (たとえば、関連するタスクのグループが同一プロセッサ ノードでの実行によって恩恵を受ける場合) に使用します。|  
|[軽量タスク](../../parallel/concrt/lightweight-tasks.md)|軽量タスクの役割について説明します。 軽量タスクは、既存のコードを改変して同時実行ランタイムのスケジュール機能を使用する場合に有用です。|  
|[コンテキスト](../../parallel/concrt/contexts.md)|コンテキスト、`concurrency::wait` 関数、および `concurrency::Context` クラスの役割について説明します。 この機能は、コンテキストのブロック、ブロック解除、および譲渡のタイミングを制御する必要がある場合や、アプリケーションでオーバーサブスクリプションを有効にする場合に使用します。|  
|[メモリ管理関数](../../parallel/concrt/memory-management-functions.md)|`concurrency::Alloc` 関数と `concurrency::Free` 関数について説明します。 これらの関数を使用すると、同時実行方式でメモリの割り当てと解放が行われるため、メモリ パフォーマンスが向上します。|  
|[その他の同時実行モデルとの比較](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md)|プリエンプティブ スケジュール メカニズムと協調スケジュール メカニズムの違いについて説明します。|  
|[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|アプリケーションで各種の並列パターン (並列アルゴリズムなど) を使用する方法について説明します。|  
|[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)|アプリケーションで非同期エージェントを使用する方法について説明します。|  
|[同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)|並列プログラミングを容易にする同時実行ランタイムについて説明します。また、関連トピックへのリンクを示します。|

