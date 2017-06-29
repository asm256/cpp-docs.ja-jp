---
title: "CMFCRibbonButton クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonButton
- AFXRIBBONBUTTON/CMFCRibbonButton
- AFXRIBBONBUTTON/CMFCRibbonButton::CMFCRibbonButton
- AFXRIBBONBUTTON/CMFCRibbonButton::AddSubItem
- AFXRIBBONBUTTON/CMFCRibbonButton::CanBeStretched
- AFXRIBBONBUTTON/CMFCRibbonButton::CleanUpSizes
- AFXRIBBONBUTTON/CMFCRibbonButton::ClosePopupMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::DrawBottomText
- AFXRIBBONBUTTON/CMFCRibbonButton::DrawImage
- AFXRIBBONBUTTON/CMFCRibbonButton::DrawRibbonText
- AFXRIBBONBUTTON/CMFCRibbonButton::FindSubItemIndexByID
- AFXRIBBONBUTTON/CMFCRibbonButton::GetCommandRect
- AFXRIBBONBUTTON/CMFCRibbonButton::GetCompactSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetIcon
- AFXRIBBONBUTTON/CMFCRibbonButton::GetImageIndex
- AFXRIBBONBUTTON/CMFCRibbonButton::GetImageSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetIntermediateSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::GetMenuRect
- AFXRIBBONBUTTON/CMFCRibbonButton::GetRegularSize
- AFXRIBBONBUTTON/CMFCRibbonButton::GetSubItems
- AFXRIBBONBUTTON/CMFCRibbonButton::GetTextRowHeight
- AFXRIBBONBUTTON/CMFCRibbonButton::GetToolTipText
- AFXRIBBONBUTTON/CMFCRibbonButton::HasCompactMode
- AFXRIBBONBUTTON/CMFCRibbonButton::HasIntermediateMode
- AFXRIBBONBUTTON/CMFCRibbonButton::HasLargeMode
- AFXRIBBONBUTTON/CMFCRibbonButton::HasMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::IsAlwaysDrawBorder
- AFXRIBBONBUTTON/CMFCRibbonButton::IsAlwaysLargeImage
- AFXRIBBONBUTTON/CMFCRibbonButton::IsApplicationButton
- AFXRIBBONBUTTON/CMFCRibbonButton::IsCommandAreaHighlighted
- AFXRIBBONBUTTON/CMFCRibbonButton::IsDefaultCommand
- AFXRIBBONBUTTON/CMFCRibbonButton::IsDefaultPanelButton
- AFXRIBBONBUTTON/CMFCRibbonButton::IsDrawTooltipImage
- AFXRIBBONBUTTON/CMFCRibbonButton::IsLargeImage
- AFXRIBBONBUTTON/CMFCRibbonButton::IsMenuAreaHighlighted
- AFXRIBBONBUTTON/CMFCRibbonButton::IsMenuOnBottom
- AFXRIBBONBUTTON/CMFCRibbonButton::IsPopupDefaultMenuLook
- AFXRIBBONBUTTON/CMFCRibbonButton::IsRightAlignMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::IsSingleLineText
- AFXRIBBONBUTTON/CMFCRibbonButton::OnCalcTextSize
- AFXRIBBONBUTTON/CMFCRibbonButton::OnDrawBorder
- AFXRIBBONBUTTON/CMFCRibbonButton::OnDraw
- AFXRIBBONBUTTON/CMFCRibbonButton::OnFillBackground
- AFXRIBBONBUTTON/CMFCRibbonButton::RemoveAllSubItems
- AFXRIBBONBUTTON/CMFCRibbonButton::RemoveSubItem
- AFXRIBBONBUTTON/CMFCRibbonButton::SetACCData
- AFXRIBBONBUTTON/CMFCRibbonButton::SetAlwaysLargeImage
- AFXRIBBONBUTTON/CMFCRibbonButton::SetDefaultCommand
- AFXRIBBONBUTTON/CMFCRibbonButton::SetDescription
- AFXRIBBONBUTTON/CMFCRibbonButton::SetImageIndex
- AFXRIBBONBUTTON/CMFCRibbonButton::SetMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::SetParentCategory
- AFXRIBBONBUTTON/CMFCRibbonButton::SetRightAlignMenu
- AFXRIBBONBUTTON/CMFCRibbonButton::SetText
- AFXRIBBONBUTTON/CMFCRibbonButton::OnClick
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonButton class
ms.assetid: 732e941c-9504-4b83-a691-d18075965d53
caps.latest.revision: 42
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 08672f10cf67a773f2af8d12130c4e3f5b497e11
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonbutton-class"></a>CMFCRibbonButton クラス
`CMFCRibbonButton` クラスは、パネル、クイック アクセス ツール バー、ポップアップ メニューなど、リボン バー要素に配置できるボタンを実装します。  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCRibbonButton : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonButton::CMFCRibbonButton](#cmfcribbonbutton)|リボン ボタン オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonButton::AddSubItem](#addsubitem)|ボタンに関連付けられたポップアップ メニューにメニュー項目を追加します。|  
|[CMFCRibbonButton::CanBeStretched](#canbestretched)|(上書き[CMFCRibbonBaseElement::CanBeStretched](../../mfc/reference/cmfcribbonbaseelement-class.md#canbestretched))。|  
|[CMFCRibbonButton::CleanUpSizes](#cleanupsizes)|(上書き[CMFCRibbonBaseElement::CleanUpSizes](../../mfc/reference/cmfcribbonbaseelement-class.md#cleanupsizes))。|  
|[CMFCRibbonButton::ClosePopupMenu](#closepopupmenu)|(上書き[CMFCRibbonBaseElement::ClosePopupMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#closepopupmenu))。|  
|[CMFCRibbonButton::DrawBottomText](#drawbottomtext)||  
|[CMFCRibbonButton::DrawImage](#drawimage)|(上書き[CMFCRibbonBaseElement::DrawImage](../../mfc/reference/cmfcribbonbaseelement-class.md#drawimage))。|  
|[CMFCRibbonButton::DrawRibbonText](#drawribbontext)||  
|[CMFCRibbonButton::FindSubItemIndexByID](#findsubitemindexbyid)|指定したコマンド ID に関連付けられたポップアップ メニュー項目のインデックスを返します。|  
|[CMFCRibbonButton::GetCommandRect](#getcommandrect)||  
|[CMFCRibbonButton::GetCompactSize](#getcompactsize)|リボン要素のコンパクト サイズを返します。 (上書き[CMFCRibbonBaseElement::GetCompactSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getcompactsize))。|  
|[CMFCRibbonButton::GetIcon](#geticon)||  
|[CMFCRibbonButton::GetImageIndex](#getimageindex)|ボタンに関連付けられているイメージのインデックスを返します。|  
|[CMFCRibbonButton::GetImageSize](#getimagesize)|リボン要素のイメージ サイズを返します。 (上書き[CMFCRibbonBaseElement::GetImageSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getimagesize))。|  
|[CMFCRibbonButton::GetIntermediateSize](#getintermediatesize)|サイズが中間状態になっているリボン要素のサイズを返します。 (上書き[CMFCRibbonBaseElement::GetIntermediateSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getintermediatesize))。|  
|[CMFCRibbonButton::GetMenu](#getmenu)|リボン ボタンに割り当てられている Windows メニューのハンドルを返します。|  
|[CMFCRibbonButton::GetMenuRect](#getmenurect)||  
|[CMFCRibbonButton::GetRegularSize](#getregularsize)|リボン要素の標準サイズを返します。 (上書き[CMFCRibbonBaseElement::GetRegularSize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize))。|  
|[CMFCRibbonButton::GetSubItems](#getsubitems)||  
|[CMFCRibbonButton::GetTextRowHeight](#gettextrowheight)||  
|[CMFCRibbonButton::GetToolTipText](#gettooltiptext)|リボン要素のツールヒント テキストを返します。 (上書き[CMFCRibbonBaseElement::GetToolTipText](../../mfc/reference/cmfcribbonbaseelement-class.md#gettooltiptext))。|  
|[CMFCRibbonButton::HasCompactMode](#hascompactmode)|リボン要素に簡易モードがあるかどうかを指定します。 (上書き[CMFCRibbonBaseElement::HasCompactMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hascompactmode))。|  
|[CMFCRibbonButton::HasIntermediateMode](#hasintermediatemode)|リボン要素に中間モードがあるかどうかを指定します。 (上書き[CMFCRibbonBaseElement::HasIntermediateMode](../../mfc/reference/cmfcribbonbaseelement-class.md#hasintermediatemode))。|  
|[CMFCRibbonButton::HasLargeMode](#haslargemode)|リボン要素に大モードがあるかどうかを指定します。 (上書き[CMFCRibbonBaseElement::HasLargeMode](../../mfc/reference/cmfcribbonbaseelement-class.md#haslargemode))。|  
|[CMFCRibbonButton::HasMenu](#hasmenu)|(上書き[CMFCRibbonBaseElement::HasMenu](../../mfc/reference/cmfcribbonbaseelement-class.md#hasmenu))。|  
|[CMFCRibbonButton::IsAlwaysDrawBorder](#isalwaysdrawborder)||  
|[CMFCRibbonButton::IsAlwaysLargeImage](#isalwayslargeimage)|(上書き[CMFCRibbonBaseElement::IsAlwaysLargeImage](../../mfc/reference/cmfcribbonbaseelement-class.md#isalwayslargeimage))。|  
|[CMFCRibbonButton::IsApplicationButton](#isapplicationbutton)||  
|[CMFCRibbonButton::IsCommandAreaHighlighted](#iscommandareahighlighted)||  
|[CMFCRibbonButton::IsDefaultCommand](#isdefaultcommand)|リボン ボタンの既定のコマンドが有効になっているかどうかを判断します。|  
|[CMFCRibbonButton::IsDefaultPanelButton](#isdefaultpanelbutton)||  
|[CMFCRibbonButton::IsDrawTooltipImage](#isdrawtooltipimage)||  
|[CMFCRibbonButton::IsLargeImage](#islargeimage)||  
|[CMFCRibbonButton::IsMenuAreaHighlighted](#ismenuareahighlighted)||  
|[CMFCRibbonButton::IsMenuOnBottom](#ismenuonbottom)||  
|[CMFCRibbonButton::IsPopupDefaultMenuLook](#ispopupdefaultmenulook)||  
|[CMFCRibbonButton::IsRightAlignMenu](#isrightalignmenu)|メニューを右寄せで表示するかどうかを判断します。|  
|[CMFCRibbonButton::IsSingleLineText](#issinglelinetext)||  
|[CMFCRibbonButton::OnCalcTextSize](#oncalctextsize)|(上書き[CMFCRibbonBaseElement::OnCalcTextSize](../../mfc/reference/cmfcribbonbaseelement-class.md#oncalctextsize))。|  
|[CMFCRibbonButton::OnDrawBorder](#ondrawborder)||  
|[CMFCRibbonButton::OnDraw](#ondraw)|リボン要素を描画するために、フレームワークによって呼び出されます。 (上書き[CMFCRibbonBaseElement::OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw))。|  
|[CMFCRibbonButton::OnFillBackground](#onfillbackground)||  
|[CMFCRibbonButton::RemoveAllSubItems](#removeallsubitems)|ポップアップ メニューからメニュー項目をすべて削除します。|  
|[CMFCRibbonButton::RemoveSubItem](#removesubitem)|ポップアップ メニューからメニュー項目を&1; つ削除します。|  
|[CMFCRibbonButton::SetACCData](#setaccdata)|(上書き[CMFCRibbonBaseElement::SetACCData](../../mfc/reference/cmfcribbonbaseelement-class.md#setaccdata))。|  
|[CMFCRibbonButton::SetAlwaysLargeImage](#setalwayslargeimage)|ユーザーがボタンを縮小したときに、ボタンに大きいイメージを表示するか小さいイメージを表示するかを指定します。|  
|[CMFCRibbonButton::SetDefaultCommand](#setdefaultcommand)|リボン ボタンの既定のコマンドを有効にします。|  
|[CMFCRibbonButton::SetDescription](#setdescription)|リボン要素の説明を設定します。 (上書き[CMFCRibbonBaseElement::SetDescription](../../mfc/reference/cmfcribbonbaseelement-class.md#setdescription))。|  
|[CMFCRibbonButton::SetImageIndex](#setimageindex)|ボタンのイメージにインデックスを割り当てます。|  
|[CMFCRibbonButton::SetMenu](#setmenu)|リボン ボタンにポップアップ メニューを割り当てます。|  
|[CMFCRibbonButton::SetParentCategory](#setparentcategory)|(上書き[CMFCRibbonBaseElement::SetParentCategory](../../mfc/reference/cmfcribbonbaseelement-class.md#setparentcategory))。|  
|[CMFCRibbonButton::SetRightAlignMenu](#setrightalignmenu)|ポップアップ メニューをボタンの右端に揃えて配置します。|  
|[CMFCRibbonButton::SetText](#settext)|リボン要素のテキストを設定します。 (上書き[CMFCRibbonBaseElement::SetText](../../mfc/reference/cmfcribbonbaseelement-class.md#settext))。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCRibbonButton::OnClick](#onclick)|ユーザーがボタンをクリックすると、フレームワークによって呼び出されます。|  
  
## <a name="example"></a>例  
 次の例は、`CMFCRibbonButton` クラスのさまざまなメソッドの使用方法を説明しています。 この例では、`CMFCRibbonButton` クラスのオブジェクトの構築、リボン ボタンへのポップアップ メニューの割り当て、ボタンの説明の設定、ポップアップ メニューからのメニュー項目の削除、およびボタンの端へのポップアップ メニューの右揃えの方法を示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp&#7;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_1.cpp)]  
  
## <a name="remarks"></a>コメント  
 リボンのボタンを使用して、アプリケーションで、ボタン オブジェクトを作成し、適切なリボンに追加[パネル](../../mfc/reference/cmfcribbonpanel-class.md)します。  
  
```  
CMFCRibbonPanel* pPanel = pCategory->AddPanel (
    _T("Clipboard"), // Panel name  
    m_PanelIcons.ExtractIcon (0)); // Panel icon  

// Create the first button ("Paste"):  
CMFCRibbonButton* pPasteButton = 
    new CMFCRibbonButton (ID_EDIT_PASTE, _T("Paste"), -1, 0);

// The third parameter (-1) disables small images for button.  
// This button is always displayed with a large image  
// Associate a pop-up menu with the "Paste" button:  
pPasteButton->SetMenu (IDR_CONTEXT_MENU);

// Add buttons to the panel. These buttons have only small images.  
pPanel->Add (new CMFCRibbonButton (ID_EDIT_CUT, _T("Cut"), 1));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_COPY, _T("Copy"), 2));
pPanel->Add (new CMFCRibbonButton (ID_EDIT_PAINT, _T("Paint"), 9));
```  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxribbonbutton.h  
  
##  <a name="addsubitem"></a>CMFCRibbonButton::AddSubItem  
 ボタンに関連付けられたポップアップ メニューにメニュー項目を追加します。  
  
```  
void AddSubItem(
    CMFCRibbonBaseElement* pSubItem,  
    int nIndex=-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pSubItem`  
 追加する新しい要素へのポインターを指定します。  
  
 [入力] `nIndex`  
 ボタンのメニュー項目の配列に要素を追加する位置を示すインデックスを指定しますメニュー項目の配列の末尾に要素を追加するのには-1。  
  
##  <a name="canbestretched"></a>CMFCRibbonButton::CanBeStretched  

  
```  
virtual BOOL CanBeStretched();
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cleanupsizes"></a>CMFCRibbonButton::CleanUpSizes  

  
```  
virtual void CleanUpSizes();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="closepopupmenu"></a>CMFCRibbonButton::ClosePopupMenu  

  
```  
virtual void ClosePopupMenu();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="cmfcribbonbutton"></a>CMFCRibbonButton::CMFCRibbonButton  
 リボン ボタン オブジェクトを構築します。  
  
```  
CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex=-1,  
    int nLargeImageIndex=-1,  
    BOOL bAlwaysShowDescription=FALSE);

CMFCRibbonButton(
    UINT nID,  
    LPCTSTR lpszText,  
    HICON hIcon,  
    BOOL bAlwaysShowDescription=FALSE,  
    HICON hIconSmall=NULL,  
    BOOL bAutoDestroyIcon=FALSE,  
    BOOL bAlphaBlendIcon=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nID`  
 ボタンのコマンド ID を指定します。  
  
 [入力] `lpszText`  
 ボタンのテキスト ラベルを指定します。  
  
 [入力] `nSmallImageIndex`  
 親カテゴリのイメージ リストで、ボタンの小さいイメージの&0; から始まるインデックスを指定します。  
  
 [入力] `nLargeImageIndex`  
 親カテゴリのイメージ リストで、ボタンの大きいイメージの&0; から始まるインデックスを指定します。  
  
 [入力] `hIcon`  
 アプリケーションが、ボタンのイメージとして使用するアイコンへのハンドルを指定します。  
  
### <a name="example"></a>例  
 次の例では、構築、`CMFCRibbonButton`オブジェクトです。  
  
 [!code-cpp[NVC_MFC_RibbonApp&6;](../../mfc/reference/codesnippet/cpp/cmfcribbonbutton-class_2.cpp)]  
  
##  <a name="drawbottomtext"></a>CMFCRibbonButton::DrawBottomText  

  
```  
CSize DrawBottomText(
    CDC* pDC,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `bCalcOnly`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="drawimage"></a>CMFCRibbonButton::DrawImage  

  
```  
virtual void DrawImage(
    CDC* pDC,  
    RibbonImageType type,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `type`  
 [入力] `rectImage`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="drawribbontext"></a>CMFCRibbonButton::DrawRibbonText  

  
```  
virtual int DrawRibbonText(
    CDC* pDC,  
    const CString& strText,  
    CRect rectText,  
    UINT uiDTFlags,  
    COLORREF clrText = (COLORREF)-1);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 [入力] `strText`  
 [入力] `rectText`  
 [入力] `uiDTFlags`  
 [入力] `clrText`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="findsubitemindexbyid"></a>CMFCRibbonButton::FindSubItemIndexByID  
 指定したコマンド ID に関連付けられたポップアップ メニュー項目のインデックスを返します。  
  
```  
int FindSubItemIndexByID(UINT uiID) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `uiID`  
 ポップアップ メニュー項目のコマンド ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 関連付けられているサブ項目の&0; から始まるインデックス、`uiID`です。 このようなサブ項目が存在しない場合は-1 を返します。  
  
##  <a name="getcommandrect"></a>CMFCRibbonButton::GetCommandRect  

  
```  
CRect GetCommandRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getcompactsize"></a>CMFCRibbonButton::GetCompactSize  

  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="geticon"></a>CMFCRibbonButton::GetIcon  

  
```  
HICON GetIcon(BOOL bLargeIcon = TRUE) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bLargeIcon`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getimageindex"></a>CMFCRibbonButton::GetImageIndex  
 ボタンに関連付けられているイメージのインデックスを返します。  
  
```  
int GetImageIndex(BOOL bLargeImage) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bLargeImage`  
 場合`TRUE`、サイズの大きなイメージが含まれています。 それ以外の場合、イメージのインデックスが返されます小さいイメージを含むイメージ リスト内のイメージ リストのイメージのインデックスを返します。  
  
### <a name="return-value"></a>戻り値  
 関連付けられているイメージ リスト内のボタンのイメージのインデックス。  
  
##  <a name="getimagesize"></a>CMFCRibbonButton::GetImageSize  

  
```  
virtual CSize GetImageSize(RibbonImageType type) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `type`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getintermediatesize"></a>CMFCRibbonButton::GetIntermediateSize  

  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getmenu"></a>CMFCRibbonButton::GetMenu  
 リボン ボタンに割り当てられている Windows メニューのハンドルを返します。  
  
```  
HMENU GetMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ボタンに割り当てられている Windows メニューへのハンドル`NULL`かどうかは、割り当てられたメニューはありません。  
  
##  <a name="getmenurect"></a>CMFCRibbonButton::GetMenuRect  

  
```  
CRect GetMenuRect() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getregularsize"></a>CMFCRibbonButton::GetRegularSize  

  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="getsubitems"></a>CMFCRibbonButton::GetSubItems  

  
```  
const CArray<CMFCRibbonBaseElement*, CMFCRibbonBaseElement*>& GetSubItems() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettextrowheight"></a>CMFCRibbonButton::GetTextRowHeight  

  
```  
int GetTextRowHeight() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettooltiptext"></a>CMFCRibbonButton::GetToolTipText  

  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hascompactmode"></a>CMFCRibbonButton::HasCompactMode  

  
```  
virtual BOOL HasCompactMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasintermediatemode"></a>CMFCRibbonButton::HasIntermediateMode  

  
```  
virtual BOOL HasIntermediateMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="haslargemode"></a>CMFCRibbonButton::HasLargeMode  

  
```  
virtual BOOL HasLargeMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="hasmenu"></a>CMFCRibbonButton::HasMenu  

  
```  
virtual BOOL HasMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isalwaysdrawborder"></a>CMFCRibbonButton::IsAlwaysDrawBorder  

  
```  
virtual BOOL IsAlwaysDrawBorder() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isalwayslargeimage"></a>CMFCRibbonButton::IsAlwaysLargeImage  

  
```  
virtual BOOL IsAlwaysLargeImage() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isapplicationbutton"></a>CMFCRibbonButton::IsApplicationButton  

  
```  
virtual BOOL IsApplicationButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="iscommandareahighlighted"></a>CMFCRibbonButton::IsCommandAreaHighlighted  

  
```  
virtual BOOL IsCommandAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdefaultcommand"></a>CMFCRibbonButton::IsDefaultCommand  
 リボンのボタンの既定のコマンドが有効になっているかどうかを指定します。  
  
```  
BOOL IsDefaultCommand() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`リボンのボタンの既定のコマンドを有効にした場合`FALSE`それ以外の場合。  
  
##  <a name="isdefaultpanelbutton"></a>CMFCRibbonButton::IsDefaultPanelButton  

  
```  
virtual BOOL IsDefaultPanelButton() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isdrawtooltipimage"></a>CMFCRibbonButton::IsDrawTooltipImage  

  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="islargeimage"></a>CMFCRibbonButton::IsLargeImage  

  
```  
BOOL IsLargeImage() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ismenuareahighlighted"></a>CMFCRibbonButton::IsMenuAreaHighlighted  

  
```  
virtual BOOL IsMenuAreaHighlighted() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ismenuonbottom"></a>CMFCRibbonButton::IsMenuOnBottom  

  
```  
BOOL IsMenuOnBottom() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ispopupdefaultmenulook"></a>CMFCRibbonButton::IsPopupDefaultMenuLook  

  
```  
virtual BOOL IsPopupDefaultMenuLook() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="isrightalignmenu"></a>CMFCRibbonButton::IsRightAlignMenu  
 メニューが右揃えするかどうかを指定します。  
  
```  
BOOL IsRightAlignMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE`メニューが右揃えの場合それ以外の場合`FALSE`します。  
  
##  <a name="issinglelinetext"></a>CMFCRibbonButton::IsSingleLineText  

  
```  
BOOL IsSingleLineText() const;  
```  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="oncalctextsize"></a>CMFCRibbonButton::OnCalcTextSize  

  
```  
virtual void OnCalcTextSize(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onclick"></a>CMFCRibbonButton::OnClick  
 ユーザーがボタンをクリックすると、フレームワークによって呼び出されます。  
  
```  
virtual void OnClick(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `point`  
 マウスのクリックの位置を指定します。  
  
### <a name="remarks"></a>コメント  
 このイベントを処理する場合は、派生クラスでは、このメソッドをオーバーライドします。  
  
##  <a name="ondraw"></a>CMFCRibbonButton::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="ondrawborder"></a>CMFCRibbonButton::OnDrawBorder  

  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="onfillbackground"></a>CMFCRibbonButton::OnFillBackground  

  
```  
virtual COLORREF OnFillBackground(CDC* pDC);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
##  <a name="removeallsubitems"></a>CMFCRibbonButton::RemoveAllSubItems  
 ポップアップ メニューからメニュー項目をすべて削除します。  
  
```  
void RemoveAllSubItems();
```  
  
##  <a name="removesubitem"></a>CMFCRibbonButton::RemoveSubItem  
 ポップアップ メニューからメニュー項目を&1; つ削除します。  
  
```  
BOOL RemoveSubItem(int nIndex);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 削除するメニュー項目の&0; から始まるインデックスを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE`指定した項目が正常に削除されている場合それ以外の場合`FALSE`場合`nIndex`が負の値またはポップアップ メニューのメニュー項目の数を超えています。  
  
##  <a name="setaccdata"></a>CMFCRibbonButton::SetACCData  
 リボン ボタンのアクセシビリティ データを設定します。  
  
```  
virtual BOOL SetACCData(
    CWnd* pParent,  
    CAccessibilityData& data);  
```  
  
### <a name="parameters"></a>パラメーター  
 `pParent`  
 リボン要素の親ウィンドウ。  
  
 `data`  
 リボン要素のアクセシビリティ データ。  
  
### <a name="return-value"></a>戻り値  
 成功した場合は `TRUE` を、それ以外の場合は FALSE を返します。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setalwayslargeimage"></a>CMFCRibbonButton::SetAlwaysLargeImage  
 ユーザーがボタンを縮小したときに、ボタンに大きいイメージを表示するか小さいイメージを表示するかを指定します。  
  
```  
void SetAlwaysLargeImage(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 場合`TRUE`ボタンは、大きな画像を表示します。 それ以外の場合、ボタンには、小さいイメージが表示されます。  
  
##  <a name="setdefaultcommand"></a>CMFCRibbonButton::SetDefaultCommand  
 リボン ボタンの既定のコマンドを有効にします。  
  
```  
void SetDefaultCommand(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 場合`TRUE`ボタンは既定のコマンドを実行できます。 場合`FALSE`ボタンは既定のコマンドを実行できません。  
  
### <a name="remarks"></a>コメント  
 `bSet`ボタンがメニューには、ときにのみ。 場合`bSet`は`TRUE`ボタンは既定のコマンドを実行できる、およびユーザーがボタンの右端にある矢印にクリックした場合にのみ割り当てられているポップアップ メニューが表示されます。 それ以外の場合、ボタンは既定のコマンドを実行できませんし、ユーザーがクリックしたボタンの領域に関係なく、ポップアップ メニューが表示されます。  
  
##  <a name="setdescription"></a>CMFCRibbonButton::SetDescription  

  
```  
virtual void SetDescription(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszText`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setimageindex"></a>CMFCRibbonButton::SetImageIndex  
 ボタンのイメージにインデックスを割り当てます。  
  
```  
void SetImageIndex(
    int nIndex,  
    BOOL bLargeImage);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nIndex`  
 イメージのインデックスを指定します。  
  
 [入力] `bLargeImage`  
 場合`TRUE`、指定したインデックスが大きいイメージの一覧を参照します。 それ以外の場合、インデックスは、小さいイメージの一覧を参照します。  
  
##  <a name="setmenu"></a>CMFCRibbonButton::SetMenu  
 リボン ボタンにポップアップ メニューを割り当てます。  
  
```  
void SetMenu(
    HMENU hMenu,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);

void SetMenu(
    UINT uiMenuResID,  
    BOOL bIsDefaultCommand=FALSE,  
    BOOL bRightAlign=FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `hMenu`  
 Windows メニューへのハンドル。  
  
 `bIsDefaultCommand`  
 場合`TRUE`ボタンは既定のコマンドを実行できます。 それ以外の場合、ボタンがポップアップ メニューを表示します。  
  
 `bRightAlign`  
 場合`TRUE`メニューが右揃え。 それ以外の場合、メニューは、左揃えにします。  
  
 `uiMenuResID`  
 メニュー リソースの id。  
  
### <a name="remarks"></a>コメント  
 アプリケーションでは、ボタン、メニューが割り当てられ、ボタンの右側に、矢印が表示されます。 場合`bIsDefaultCommand`は`TRUE`メニューは、ユーザーが矢印にクリックした場合にのみ表示されます。 ユーザーには、ボタンがクリックすると、既定のコマンドが実行されます。 場合`bIsDefaultCommand`は`FALSE`、ボタンをクリックして、メニューが表示されます。  
  
##  <a name="setparentcategory"></a>CMFCRibbonButton::SetParentCategory  

  
```  
virtual void SetParentCategory(CMFCRibbonCategory* pParent);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pParent`  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setrightalignmenu"></a>CMFCRibbonButton::SetRightAlignMenu  
 ポップアップ メニュー ボタンの端に揃えて配置します。  
  
```  
void SetRightAlignMenu(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bSet`  
 場合`TRUE`メニューが右揃え。 それ以外の場合、メニューが、左揃え  
  
##  <a name="settext"></a>CMFCRibbonButton::SetText  

  
```  
virtual void SetText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lpszText`  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
