---
title: "エディット コントロール ハンドラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ON_EN_ERRSPACE
- ON_EN_UPDATE
- ON_EN_VSCROLL
- ON_EN_HSCROLL
- ON_EN_KILLFOCUS
- ON_EN_MAXTEXT
- ON_EN_SETFOCUS
- ON_EN_CHANGE
dev_langs: C++
helpviewer_keywords:
- ON_EN_ERRSPACE macro [MFC]
- ON_EN_SETFOCUS macro [MFC]
- ON_EN_UPDATE macro [MFC]
- ON_EN_MAXTEXT macro [MFC]
- ON_EN_CHANGE macro [MFC]
- ON_EN_HSCROLL macro [MFC]
- ON_EN_VSCROLL macro [MFC]
- ON_EN_KILLFOCUS macro [MFC]
- edit controls [MFC], edit control handlers
ms.assetid: 55b88b5e-12b5-4422-b03e-c8c2f27d095c
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7599a7ca1c486de453fb3404fa69cab8a09e2d0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="edit-control-handlers"></a>エディット コントロール ハンドラー
関数プロトタイプに対応するマップ エントリを次に示します。  
  
|マップのエントリ|関数プロトタイプ|  
|---------------|------------------------|  
|ON_EN_CHANGE ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
|ON_EN_ERRSPACE ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
|ON_EN_HSCROLL ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
|ON_EN_KILLFOCUS ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
|ON_EN_MAXTEXT ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
|ON_EN_SETFOCUS ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
|ON_EN_UPDATE ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
|ON_EN_VSCROLL ( \<id >、 \<memberFxn >)|afx_msg void memberFxn ();|  
  
## <a name="see-also"></a>関連項目  
 [メッセージ マップ](../../mfc/reference/message-maps-mfc.md)

