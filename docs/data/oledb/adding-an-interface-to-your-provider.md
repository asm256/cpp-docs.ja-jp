---
title: "プロバイダーへのインターフェイスの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9a5a383e32a4fa5cb626dee499d5b2262abe37c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="adding-an-interface-to-your-provider"></a>プロバイダーへのインターフェイスの追加
(通常のデータ ソース、行セット、コマンド、またはセッション オブジェクトに OLE DB プロバイダー ウィザードによって作成された) インターフェイスを追加するオブジェクトを決定します。 オブジェクトのインターフェイスを追加する必要がありますが、プロバイダーは現在サポートしていない 1 つである可能性がします。 その場合は、ATL OLE DB プロバイダー ウィザード、オブジェクトを作成するを実行します。 クラス ビュー でプロジェクトを右クリックし、をクリックして**クラスの追加**から、**追加** メニューをクリックして**ATL OLE DB プロバイダー**です。 別のディレクトリにインターフェイスのコードを配置し、プロバイダー プロジェクトにファイルをコピーする可能性があります。  
  
 インターフェイスをサポートする新しいクラスを作成した場合は、そのクラスから継承するオブジェクトを確認します。 たとえば、クラスを追加する場合があります**IRowsetIndexImpl**行セット オブジェクトに。  
  
```  
template <class Creator>  
class CAgentRowset :   
public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
   public IRowsetIndexImpl< ... >   
```  
  
 インターフェイスを追加**COM_MAP** COM_INTERFACE_ENTRY マクロを使用してオブジェクトにします。 マップがない場合は、1 つを作成します。 例:  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 行セット オブジェクトのチェーンの親のマップ オブジェクトのオブジェクトが親クラスに委任できるようにします。 この例では、マップに COM_INTERFACE_ENTRY_CHAIN マクロを追加します。  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)