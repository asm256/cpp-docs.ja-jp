---
title: "IRowsetImpl::m_bCanScrollBack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl::m_bCanScrollBack"
  - "ATL::IRowsetImpl::m_bCanScrollBack"
  - "IRowsetImpl.m_bCanScrollBack"
  - "ATL.IRowsetImpl.m_bCanScrollBack"
  - "m_bCanScrollBack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bCanScrollBack"
ms.assetid: 69de3179-bf56-415e-935f-e98bcb34debe
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::m_bCanScrollBack
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロバイダーがカーソルを前後逆にスクロールすることができるかどうかを示します。  
  
## 構文  
  
```  
  
unsigned  m_bCanScrollBack:1;  
  
```  
  
## 解説  
 **DBPROPSET\_ROWSET** グループのプロパティを **DBPROP\_CANSCROLLBACKWARDS** にリンクされます。  プロバイダーは true と **m\_bCanFetchBackwards** の **DBPROP\_CANSCROLLBACKWARDS** をサポートする必要があります。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetImpl クラス](../Topic/IRowsetImpl%20Class.md)   
 [IRowsetImpl::m\_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)