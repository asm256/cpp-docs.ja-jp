---
title: "_bstr_t::Attach |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _bstr_t::Attach
dev_langs: C++
helpviewer_keywords: Attach method [C++]
ms.assetid: 8cad867e-40fc-435b-841f-0d412c2f58d3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dbb3f0352302d366d57ba94b745aa3dd18a4bb8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="bstrtattach"></a>_bstr_t::Attach
**Microsoft 固有の仕様**  
  
 `_bstr_t` ラッパーを `BSTR` にリンクします。  
  
## <a name="syntax"></a>構文  
  
```  
  
      void Attach(  
   BSTR s  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *s*  
 `BSTR` 変数に関連付けられる、または割り当てられる `_bstr_t`。  
  
## <a name="remarks"></a>コメント  
 `_bstr_t` が以前別の `BSTR` にアタッチされている場合、`_bstr_t` は、`BSTR` の他の変数が `_bstr_t` を使用していない場合 `BSTR` リソースをクリーンアップします。  
  
## <a name="example"></a>例  
 参照してください[_bstr_t::assign](../cpp/bstr-t-assign.md)使用例については**アタッチ**です。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_bstr_t クラス](../cpp/bstr-t-class.md)