---
title: "Visual C ツールおよび Visual Studio のエディションで機能 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- versions [C++]
- Visual C++, versions
- editions [C++]
ms.assetid: 3d88607b-9cc4-490a-8d4c-31ee7610a26f
caps.latest.revision: "51"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 37f1eed2287c8fe655a124b1f76f48a203ab1607
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="visual-c-tools-and-features-in-visual-studio-editions"></a>Visual C ツールおよび Visual Studio のエディションの機能
Visual Studio で使用できる Visual C++ の機能を次の表に示します。 セル内の X は機能が使用できることを示し、空のセルは機能が使用できないことを示します。 かっこ内の説明は機能が制限付きで使用できることを示します。  
  
## <a name="platforms"></a>プラットフォーム  
  
||||||  
|-|-|-|-|-|  
|プラットフォーム|Visual Studio Express for Windows 10|Visual Studio Express for Windows Desktop|Visual Studio Community/Professional|Visual Studio Enterprise|  
|Windows デスクトップ||X|X|X|  
|ユニバーサル Windows プラットフォーム ((電話、タブレット、PC、Xbox、IoT、HoloLens))|X||X|X|  
|Windows ストア 8.1|||X|X|  
|Windows Phone 8.0|||X|X|  
|Android|||X|X|  
|iOS|||X|X|  
  
## <a name="compilers"></a>コンパイラ  
  
|コンパイラ|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|32 ビット X86 コンパイラ|X|X|X|X|  
|X86_arm cross-compiler|X||X|X|  
|64 ビット [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] コンパイラ|||X|X|  
|X86_ [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] cross-compiler|X|X|X|X|  
  
## <a name="libraries-and-headers"></a>ライブラリおよびヘッダー  
  
|ライブラリまたはヘッダー|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|Windows ヘッダー、ライブラリ、CRT ライブラリ|(X)|X|X|X|  
|C++ 標準ライブラリ|X|X|X|X|  
|[ATL]|||X|X|  
|MFC|||X|X|  
|.NET Framework クラス ライブラリ||X|X|X|  
|.NET 用 C++ サポート ライブラリ||X|X|X|  
|OpenMP|X|X|X|X|  
  
## <a name="project-templates"></a>プロジェクト テンプレート  
  
|テンプレート|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|--------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|UWP、Windows 8.1、Windows Phone 8.0 向け XAML テンプレート|X||X|X|  
|Direct3D アプリケーション|X||X|X|  
|DLL (Windows ストア アプリ)|X||X|X|  
|スタティック ライブラリ (Windows ストア アプリ)|X||X|X|  
|Windows ランタイム コンポーネント|X||X|X|  
|単体テスト ライブラリ (Windows ストア アプリ)|X||X|X|  
|ATL プロジェクト|||X|X|  
|クラス ライブラリ (CLR)||X|X|X|  
|CLR コンソール アプリケーション||X|X|X|  
|CLR 空プロジェクト||X|X|X|  
|カスタム ウィザード|||X|X|  
|空のプロジェクト||X|X|X|  
|メイクファイル プロジェクト||X|X|X|  
|MFC ActiveX コントロール|||X|X|  
|MFC アプリケーション|||X|X|  
|MFC DLL|||X|X|  
|Test Project|X|X|X|X|  
|Win32 コンソール アプリケーション||X|X|X|  
|Win32 プロジェクト||X|X|X|  
  
## <a name="tools"></a>ツール  
  
|ツール|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|----------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|インクリメンタル リンカー (Link.exe)|X|X|X|X|  
|Program Maintenance Utility (Nmake.exe)||X|X|X|  
|Lib ジェネレーター (Lib.exe)|X|X|X|X|  
|Windows リソース コンパイラ (Rc.exe)|X|X|X|X|  
|Windows Resource to Object Converter (CvtRes.exe)||X|X|X|  
|Browse Information Maintenance Utility (BscMake.exe)|X|X|X|X|  
|C++ Name Undecorator (Undname.exe)|X|X|X|X|  
|COFF/PE Dumper (Dumpbin.exe)|X|X|X|X|  
|COFF/PE Editor (Editbin.exe)|X|X|X|X|  
|MASM (Ml.exe)|||X|X|  
|Spy++|||X|X|  
|ErrLook|||X|X|  
|AtlTrace|||X|X|  
|Devenv.com|||X|X|  
|推論規則|||X|X|  
|VCBuild .vcproj プロジェクトの MSBuild (VCUpgrade.exe) へのアップグレード|X|X|X|X|  
|ガイド付き最適化のプロファイル|||X|X|  
  
## <a name="debugging-features"></a>デバッグ機能  
  
|デバッグ機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|-----------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|ネイティブ デバッグ|X|X|X|X|  
|natvis (ネイティブ型の視覚エフェクト)|X|X|X|X|  
|グラフィックスのデバッグ|X||X|X|  
|マネージ デバッグ||X|X|X|  
|GPU 使用率|X||X|X|  
|メモリ使用量|X||X|X|  
|リモート デバッグ|X|X|X|X|  
|SQL デバッグ|||X|X|  
|スタティック コード分析|制限|制限|X|X|  
  
## <a name="designers-and-editors"></a>デザイナーおよびエディター  
  
|デザイナーまたはエディター|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|XAML デザイナー|X||X|X|  
|CSS スタイル デザイナー/エディター|X|X|X|X|  
|HTML デザイナー/エディター|X|X|X|X|  
|XML エディター|X|X|X|X|  
|ソース コード エディター|X|X|X|X|  
|生産性機能: リファクタリング、IntelliSense、C++ コードの書式設定|X|X|X|X|  
|Windows フォーム デザイナー||X|X|X|  
|データ デザイナー|||X|X|  
|ネイティブ リソース エディター (.rc ファイル)|||X|X|  
|リソース エディター|X|X|X|X|  
|モデル エディター|X||X|X|  
|シェーダー デザイナー|X||X|X|  
  
## <a name="data-features"></a>データ機能  
  
|データ機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Premium|Visual Studio Enterprise|  
|------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|---------------------------|------------------------------|  
|データ デザイナー|||X|X|X|  
|データ オブジェクト|||X|X|X|  
|Web サービス|||X|X|X|  
|サーバー エクスプローラー|||X|X|X|  
  
## <a name="build-and-project-systems"></a>ビルド システムとプロジェクト システム  
  
|ビルドまたはプロジェクトの機能|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|コマンド ライン ビルド (msbuild.exe)|X|X|X|X|  
|ネイティブ マルチ ターゲット||X|X|X|  
|マネージ マルチ ターゲット||X|X|X|  
|平行ビルド|X|X|X|X|  
|カスタマイズのビルド|X|X|X|X|  
|プロパティ ページの機能拡張|X|X|X|X|  
  
## <a name="automation-and-extensibility"></a>オートメーションおよび機能拡張  
  
|オートメーションおよび機能拡張|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|----------------------------------|---------------------------------------|-----------------------------------------------|---------------------------------------------|------------------------------|  
|機能拡張オブジェクト モデル|||X|X|  
|コード モデル|||X|X|  
|プロジェクト モデル|||X|X|  
|リソース エディター モデル|||X|X|  
|ウィザード モデル|||X|X|  
|デバッガー オブジェクト モデル|||X|X|  
  
## <a name="application-lifecycle-management-tools"></a>アプリケーション ライフサイクル管理ツール  
  
||||||  
|-|-|-|-|-|  
|ツール|Visual Studio Express for Windows|Visual Studio Express for Windows Desktop|Visual Studio Professional/Community|Visual Studio Enterprise|  
|単体テスト (ネイティブ フレームワーク)|X|X|X|X|  
|単体テスト (マネージ フレームワーク)||X|X|X|  
|コード カバレッジ||||X|  
|手動テスト||||X|  
|探索的テスト||||X|  
|テスト ケース管理||||X|  
|コード マップと依存関係グラフ|||読み取り専用|X|  
|コード マップ デバッグ||||X|  
  
## <a name="see-also"></a>関連項目  
 [Visual Studio のインストール](/visualstudio/install/install-visual-studio)   
 [Visual Studio の新機能](/visualstudio/ide/whats-new-in-visual-studio)   
 [Visual C プロジェクトの種類](../ide/visual-cpp-project-types.md)   
 [Visual Database Tools のエディション](http://msdn.microsoft.com/en-us/a7689adc-f16b-4cc7-b6fe-39ca0c711161)