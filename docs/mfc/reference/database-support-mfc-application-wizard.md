---
title: "データベース サポートは、MFC アプリケーション ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.database
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 875df8f8205d132cf6bcafe536c221876a5e3e51
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="database-support-mfc-application-wizard"></a>[データベース サポート] (MFC アプリケーション ウィザード)
このページで、データベースのレベルを指定できるようにするオプションは、プロジェクトの (さらに、データ ソースを必要な場合) をサポートします。  
  
 **データベースのサポート**  
 データベース プロジェクトのサポートのレベルを設定します。  
  
|オプション|説明|  
|------------|-----------------|  
|**None**|データベースのサポートを提供しません。 これは、既定の設定です。|  
|**ヘッダー ファイルのみ**|アプリケーションの基本的なレベルのデータベースのサポートを提供します。 ODBC のサポートを選択した場合**クライアント型**、MFC アプリケーション ウィザードにはで、プロジェクトで AFXDB ヘッダー ファイルが含まれます。H. リンク ライブラリを追加しますが、任意のデータベース固有のクラスは作成されません。 レコード セットを後で作成しを使用して確認およびレコードを更新できます。 OLE DB サポートを選択した場合**クライアント型**、次のヘッダー ファイルが含まれています: ATLBASE です。H AFXOLEDB です。H ATLPLUS です。H|  
|**ファイル サポートのないデータベース ビュー**|データベースのヘッダー ファイル、リンク ライブラリ、レコード ビューとレコード セットが含まれます。 (アプリケーションに対してのみ使用可能な**ドキュメント/ビュー アーキテクチャ サポート**で選択したオプション、[アプリケーションの種類](../../mfc/reference/application-type-mfc-application-wizard.md)ページです)。このオプションには、ドキュメントのサポートがないシリアル化のサポートが含まれています。 データベース ビューを含めるように選択する場合は、データのソースを指定する必要があります。|  
|**ファイルのサポートのあるデータベース ビュー**|データベースのヘッダー ファイル、リンク ライブラリ、レコード ビューとレコード セットが含まれます。 (アプリケーションに対してのみ使用可能な**ドキュメント/ビュー アーキテクチャ サポート**で選択したオプション、**アプリケーションの種類**ページです)。このオプションを使用するなど、ユーザー プロファイル ファイルを更新するドキュメントのシリアル化をサポートします。 データベース アプリケーションでファイルごとのため必要はありませんシリアル化ではなく、通常、レコード単位で動作します。 ただし、シリアル化のための特別な用途があります。 データベース ビューを含めるように選択する場合は、データのソースを指定する必要があります。|  
  
> [!NOTE]
>  **データベース サポート**いずれかを選択する場合は、**ファイル サポートのないデータベース ビュー**または**ファイル サポートのあるデータベース ビュー**、ビュー クラスの派生ごとに、異なります**クライアントの種類**次のように、選択します。  
  
-   選択した場合**ODBC** **クライアント型**、アプリケーションのビュー クラスから派生し、 [CRecordView](../../mfc/reference/crecordview-class.md)です。 このクラスに関連付けられている、 [CRecordset](../../mfc/reference/crecordset-class.md)-派生クラスで、MFC アプリケーション ウィザードが行うも作成されます。 このオプションでは、表示、レコード セット内のレコードを更新して、レコード ビューを使用するフォーム ベースのアプリケーションを提供します。  
  
-   選択した場合**OLE DB** **クライアントの種類**、ビュー クラスから派生し、 [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)、関連付けられていると、 [CTable](../../data/oledb/ctable-class.md)または[CCommand](../../data/oledb/ccommand-class.md)-クラスを派生します。  
  
 **クライアントの種類**  
 プロジェクトでは OLE DB または ODBC のクラスを使用しているかどうかを示します。  
  
|オプション|説明|  
|------------|-----------------|  
|**OLE DB**|このオプションを選択するをクリックすると、**データ ソース**ボタンで呼び出され、**データ リンク プロパティ**OLE DB データ ソースへの接続を作成するためのウィザード。|  
|**ODBC**|このオプションを選択するをクリックすると、**データ ソース**ボタンで呼び出され、**データ ソースの選択**ODBC データ ソースへの接続を作成するためのウィザード。|  
  
 **データ ソース**  
 クリックして、**データ ソース**指定のドライバーまたはプロバイダーとデータベースを使用してデータ ソースを設定するボタンをクリックします。 OLE DB を選択した場合、**クライアント型**オプション、このボタンを表示、**データ リンク プロパティ** ダイアログ ボックス。 ODBC を選択した場合、**クライアント型**オプション、このボタンは、提供、**データ ソースの選択** ダイアログ ボックス。 このオプションは、アプリケーションでデータベース ビューを含めるように選択する場合にのみ使用できます。  
  
|オプション|説明|  
|------------|-----------------|  
|**データ リンク プロパティ**(OLE DB)|指定した OLE DB プロバイダーを使用して、指定したデータ ソースを確立します。 OLE DB プロバイダー、データ、データ ソース、ログオン ID、および (必要に応じて) パスワードの場所を指定する必要があります。 このダイアログ ボックスの詳細については、「**データソース**で[ATL OLE DB コンシューマー ウィザード](../../atl/reference/atl-ole-db-consumer-wizard.md)です。|  
|**データ ソースの選択**(ODBC)|指定された ODBC ドライバーを使用して、指定したデータ ソースを確立します。 データ ソースのテーブルを選択するデータ ソースの名前を選択する必要があります。 ウィザードのメンバー変数にテーブルのすべての列をバインドする、 `CRecordset`-クラスを派生します。 このダイアログ ボックスの詳細については、「**データソース**で[MFC ODBC コンシューマー ウィザード](../../mfc/reference/mfc-odbc-consumer-wizard.md)です。|  
  
> [!NOTE]
>  Shift キーをクリックすると、以前のリリースで、**データソース**ボタンは、データ リンク (.udl) ファイルを選択できるようにファイルを開く ダイアログを開きます。 この機能は現在サポートされていません。  
  
 **属性付きデータベース クラスを生成します**  
 OLE DB クライアントのみで使用できます。 生成されたプロジェクトでデータベース クラスで属性を使用するかどうかを指定します。  
  
 **すべての列をバインドします。**  
 ODBC クライアントのみで使用できます。 選択したテーブルのすべての列がバインドされているかどうかを指定します。 このボックスをオンにすると、すべての列がバインドされます。このボックスを選択しない場合は、列がバインドされていないとレコード セット クラスで手動でバインドする必要があります。  
  
 **Type**  
 ODBC クライアントのみで使用できます。 指定するかどうか、レコード セット ダイナセットまたはスナップショットを次の表で説明します。  
  
|オプション|説明|  
|------------|-----------------|  
|**ダイナセット**|レコード セットがダイナセットであることを指定します。 ダイナセットは、クエリ対象のデータベースのデータにインデックス付きビューを提供するクエリの結果です。 ダイナセットは、元のデータを整数のインデックスのみをキャッシュし、スナップショットに比べてパフォーマンスができるようにします。 各レコードに直接インデックス ポイントは、クエリの結果として検出され、レコードが削除されたかどうかを示します。 照会されたレコードに更新された情報へのアクセスもがあります。|  
|スナップショット|レコード セットがスナップショットであることを指定します。 スナップショットはクエリの結果、1 つのポイントにおけるデータベースのビューに。 クエリの結果として検出されたすべてのレコードがキャッシュされるため、元のレコードへの変更が表示されません。|  
  
## <a name="see-also"></a>関連項目  
 [MFC アプリケーション ウィザード](../../mfc/reference/mfc-application-wizard.md)
