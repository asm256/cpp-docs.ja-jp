---
title: "CD2DMesh クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CD2DMesh
- AFXRENDERTARGET/CD2DMesh
- AFXRENDERTARGET/CD2DMesh::CD2DMesh
- AFXRENDERTARGET/CD2DMesh::Attach
- AFXRENDERTARGET/CD2DMesh::Create
- AFXRENDERTARGET/CD2DMesh::Destroy
- AFXRENDERTARGET/CD2DMesh::Detach
- AFXRENDERTARGET/CD2DMesh::Get
- AFXRENDERTARGET/CD2DMesh::IsValid
- AFXRENDERTARGET/CD2DMesh::Open
- AFXRENDERTARGET/CD2DMesh::m_pMesh
dev_langs:
- C++
helpviewer_keywords:
- CD2DMesh [MFC], CD2DMesh
- CD2DMesh [MFC], Attach
- CD2DMesh [MFC], Create
- CD2DMesh [MFC], Destroy
- CD2DMesh [MFC], Detach
- CD2DMesh [MFC], Get
- CD2DMesh [MFC], IsValid
- CD2DMesh [MFC], Open
- CD2DMesh [MFC], m_pMesh
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 4a770b6508067913aec51b8b3878f33e30eed4bb
ms.openlocfilehash: 689d8f5a98b7dc8daf225b611a5718a22d20b67c
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="cd2dmesh-class"></a>CD2DMesh クラス
ID2D1Mesh のラッパーです。  
  
## <a name="syntax"></a>構文  
  
```  
class CD2DMesh : public CD2DResource;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DMesh::CD2DMesh](#cd2dmesh)|CD2DMesh オブジェクトを構築します。|  
|[CD2DMesh:: ~ CD2DMesh](#_dtorcd2dmesh)|デストラクターです。 D2D メッシュ オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DMesh::Attach](#attach)|既存のリソースのインターフェイス オブジェクトへの接続|  
|[CD2DMesh::Create](#create)|CD2DMesh を作成します。 (上書き[CD2DResource::Create](../../mfc/reference/cd2dresource-class.md#create))。|  
|[CD2DMesh::Destroy](#destroy)|CD2DMesh オブジェクトを破棄します。 (上書き[CD2DResource::Destroy](../../mfc/reference/cd2dresource-class.md#destroy))。|  
|[CD2DMesh::Detach](#detach)|オブジェクトからリソースのインターフェイスの関連付けを解除します。|  
|[CD2DMesh::Get](#get)|返します ID2D1Mesh インターフェイス|  
|[CD2DMesh::IsValid](#isvalid)|リソースの有効性をチェック (オーバーライド[CD2DResource::IsValid](../../mfc/reference/cd2dresource-class.md#isvalid))。|  
|[CD2DMesh::Open](#open)|母集団のメッシュを開きます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DMesh::operator ID2D1Mesh *](#operator_id2d1mesh_star)|返します ID2D1Mesh インターフェイス|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CD2DMesh::m_pMesh](#m_pmesh)|ID2D1Mesh へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 `CD2DMesh`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxrendertarget.h  
  
##  <a name="_dtorcd2dmesh"></a>CD2DMesh:: ~ CD2DMesh  
 デストラクターです。 D2D メッシュ オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CD2DMesh();
```  
  
##  <a name="attach"></a>CD2DMesh::Attach  
 既存のリソースのインターフェイス オブジェクトへの接続  
  
```  
void Attach(ID2D1Mesh* pResource);
```  
  
### <a name="parameters"></a>パラメーター  
 `pResource`  
 既存のリソースのインターフェイスです。 NULL をすることはできません。  
  
##  <a name="cd2dmesh"></a>CD2DMesh::CD2DMesh  
 CD2DMesh オブジェクトを構築します。  
  
```  
CD2DMesh(
    CRenderTarget* pParentTarget,  
    BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentTarget`  
 レンダー ターゲットへのポインター。  
  
 `bAutoDestroy`  
 所有者 (pParentTarget) によって、オブジェクトが破棄されることを示します。  
  
##  <a name="create"></a>CD2DMesh::Create  
 CD2DMesh を作成します。  
  
```  
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `pRenderTarget`  
 レンダー ターゲットへのポインター。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 それ以外の場合、HRESULT エラー コードを返します。  
  
##  <a name="destroy"></a>CD2DMesh::Destroy  
 CD2DMesh オブジェクトを破棄します。  
  
```  
virtual void Destroy();
```  
  
##  <a name="detach"></a>CD2DMesh::Detach  
 オブジェクトからリソースのインターフェイスの関連付けを解除します。  
  
```  
ID2D1Mesh* Detach();
```  
  
### <a name="return-value"></a>戻り値  
 デタッチされたリソースのインターフェイスへのポインター。  
  
##  <a name="get"></a>CD2DMesh::Get  
 返します ID2D1Mesh インターフェイス  
  
```  
ID2D1Mesh* Get();
```  
  
### <a name="return-value"></a>戻り値  
 ID2D1Mesh インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
##  <a name="isvalid"></a>CD2DMesh::IsValid  
 リソースの有効性のチェック  
  
```  
virtual BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 リソースが無効である場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_pmesh"></a>CD2DMesh::m_pMesh  
 ID2D1Mesh へのポインター。  
  
```  
ID2D1Mesh* m_pMesh;  
```  
  
##  <a name="open"></a>CD2DMesh::Open  
 母集団のメッシュを開きます。  
  
```  
ID2D1TessellationSink* Open();
```  
  
### <a name="return-value"></a>戻り値  
 メッシュへの追加に使用される ID2D1TessellationSink へのポインター。  
  
##  <a name="operator_id2d1mesh_star"></a>CD2DMesh::operator ID2D1Mesh *  
 返します ID2D1Mesh インターフェイス  
  
```  
operator ID2D1Mesh*();
```   
  
### <a name="return-value"></a>戻り値  
 ID2D1Mesh インターフェイスまたはオブジェクトがまだ初期化されていない場合は、NULL へのポインター。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)

