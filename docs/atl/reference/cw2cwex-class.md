---
title: "CW2CWEX クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 5dca6b31cdd99582e727b634093c3548eef2ecc1
ms.contentlocale: ja-jp
ms.lasthandoff: 03/31/2017

---
# <a name="cw2cwex-class"></a>CW2CWEX クラス
このクラスは、文字列変換マクロによって使用`CW2CTEX`と`CT2CWEX`、および typedef`CW2W`です。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>パラメーター  
 `t_nBufferLength`  
 変換プロセスで使用するバッファーのサイズ。 既定の長さは 128 バイトです。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|コンストラクターです。|  
|[CW2CWEX:: ~ CW2CWEX](#dtor)|デストラクターです。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|変換演算子です。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|ソース文字列を格納するデータ メンバーです。|  
  
## <a name="remarks"></a>コメント  
 追加の機能が必要な場合を除き、使用`CW2CTEX`、 `CT2CWEX`、または`CW2W`コードにします。  
  
 このクラスは、安全にループで使用し、スタック オーバーフローが発生しません。 既定では、ATL 変換クラスとマクロは、変換の現在のスレッドの ANSI コード ページを使用します。  
  
 次のマクロは、このクラスに基づいています。  
  
- `CW2CTEX`  
  
- `CT2CWEX`  
  
 次の typedef は、このクラスに基づいています。  
  
- `CW2W`  
  
 これらのテキスト変換マクロの詳細については、次を参照してください。 [ATL および MFC 文字列変換マクロ](string-conversion-macros.md)です。  
  
## <a name="example"></a>例  
 参照してください[ATL および MFC 文字列変換マクロ](string-conversion-macros.md)をこれらの文字列変換マクロを使用する例についてはします。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlconv.h  
  
##  <a name="cw2cwex"></a>CW2CWEX::CW2CWEX  
 コンストラクターです。  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>パラメーター  
 `psz`  
 変換するテキスト文字列。  
  
 `nCodePage`  
 コード ページです。 このクラスでは使用されません。  
  
### <a name="remarks"></a>コメント  
 変換プロセスで使用するバッファーを割り当てます。  
  
##  <a name="dtor"></a>CW2CWEX:: ~ CW2CWEX  
 デストラクターです。  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>コメント  
 割り当てられたバッファーを解放します。  
  
##  <a name="m_psz"></a>CW2CWEX::m_psz  
 ソース文字列を格納するデータ メンバーです。  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="operator_lpcwstr"></a>CW2CWEX::operator LPCWSTR  
 変換演算子です。  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 種類としてテキスト文字列を返す**LPCWSTR です。**  
  
## <a name="see-also"></a>関連項目  
 [CA2AEX クラス](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX クラス](../../atl/reference/ca2caex-class.md)   
 [CA2WEX クラス](../../atl/reference/ca2wex-class.md)   
 [CW2AEX クラス](../../atl/reference/cw2aex-class.md)   
 [CW2WEX クラス](../../atl/reference/cw2wex-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

