---
title: "Visual C++ プロジェクトに対して作成されるファイルの種類 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ヘッダー ファイル [C++]、Visual C++ プロジェクト"
  - "ActiveX コントロール [C++]、ヘルプ ファイル"
  - "def ファイル"
  - "プロジェクト項目 [C++]、ファイル"
  - "Visual C++ プロジェクト、ファイルとディレクトリ"
  - "リソース ファイル、作成 (ウィザードで)"
  - "ファイル [C++]、拡張機能"
  - "ヘルプ ファイル、ActiveX コントロールの"
  - "Web プロジェクト [C++]、追加 (アイテムを)"
  - ".def ファイル"
  - "ライセンス (ActiveX コントロールの)"
ms.assetid: 2b0ee2e0-ae81-4185-9bb9-11da3c99a283
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Visual C++ プロジェクトに対して作成されるファイルの種類
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックでは、従来のデスクトップ アプリケーションの Visual C\+\+ プロジェクトに関連付けられているすべての種類のファイルについて説明します。 実際にプロジェクトにインクルードされるファイルは、プロジェクトの種類、およびウィザードで選択したオプションによって異なります。  
  
-   [プロジェクト ファイルとソリューション ファイル](../ide/project-and-solution-files.md)  
  
-   [CLR プロジェクト](../ide/files-created-for-clr-projects.md)  
  
-   [ATL プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/atl-program-or-control-source-and-header-files.md)  
  
-   [MFC プログラムまたはコントロールのソース ファイルとヘッダー ファイル](../ide/mfc-program-or-control-source-and-header-files.md)  
  
-   [プリコンパイル済みヘッダー ファイル](../ide/precompiled-header-files.md)  
  
-   [リソース ファイル](../ide/resource-files-cpp.md)  
  
-   [ヘルプ ファイル \(WinHelp\)](../Topic/Help%20Files%20\(WinHelp\).md)  
  
-   [ヒント ファイル](../ide/hint-files.md)  
  
 [Visual C\+\+ プロジェクトの作成](../ide/creating-desktop-projects-by-using-application-wizards.md)では、ソリューションを新しく作成する場合や、ソリューションにプロジェクトを追加する場合があります。 通常、複雑なアプリケーションの開発では、1 つのソリューションに複数のプロジェクトを作成します。  
  
 プロジェクトでは、通常、EXE ファイルまたは DLL ファイルが生成されます。 プロジェクト間で相互に依存関係を持つ場合もあります。Visual C\+\+ 環境では、ビルド処理中に、プロジェクト内部およびプロジェクト間の両方について依存関係をチェックします。 各プロジェクトにはコア ソース コードがあります。また、プロジェクトの種類に応じて、プロジェクトのさまざまな要素を格納したファイルが多数含まれることがあります。 これらのファイルの内容はファイル拡張子によって示されます。 Visual Studio 開発環境では、ファイル拡張子を使用して、ビルド時のファイル内容の処理方法を判断します。  
  
 Visual C\+\+ プロジェクトの一般的なファイルとそのファイル拡張子を次の表に示します。  
  
|ファイル拡張子|型|目次|  
|-------------|-------|--------|  
|.asmx|ソース|配置ファイル。|  
|.asp|ソース|ASP \(Active Server Page\) ファイル。|  
|.atp|プロジェクト|アプリケーション テンプレート プロジェクト ファイル。|  
|.bmp、.dib、.gif、.jpg、.jpe、.png|リソース|一般的なイメージ ファイル。|  
|.bsc|コンパイル|ブラウザー コード ファイル。|  
|.cpp、.c|ソース|アプリケーションの主要なソース コード ファイル。|  
|.cur|リソース|カーソルのビットマップ グラフィック ファイル。|  
|.dbp|プロジェクト|データベース プロジェクト ファイル。|  
|.disco|ソース|動的探索ドキュメント ファイル。 XML Web サービス探索を処理します。|  
|.exe、.dll|プロジェクト|実行可能ファイルまたはダイナミック リンク ライブラリ ファイル。|  
|.h|ソース|ヘッダー ファイルまたはインクルード ファイル。|  
|.htm、.html、.xsp、.asp、.htc、.hta、.xml|リソース|共通 Web ファイル。|  
|.HxC|プロジェクト|ヘルプ プロジェクト ファイル。|  
|.ico|リソース|アイコンのビットマップ グラフィック ファイル。|  
|.idb|コンパイル|ソース ファイルとクラス定義との依存関係情報が含まれているステート ファイル。最小リビルドとインクリメンタル コンパイルのときにコンパイラで使用します。 .idb ファイルの名前は [\/Fd](../build/reference/fd-program-database-file-name.md) コンパイラ オプションで指定します。 詳細については、「[\/Gm \(簡易リビルドの有効化\)](../build/reference/gm-enable-minimal-rebuild.md)」を参照してください。|  
|.idl|コンパイル|インターフェイス定義言語ファイル。 詳しくは、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の「[インターフェイス定義 \(IDL\) ファイル](http://msdn.microsoft.com/library/windows/desktop/aa378712)」をご覧ください。|  
|.ilk|リンク|インクリメンタル リンク ファイル。 詳しくは、「[\/INCREMENTAL](../build/reference/incremental-link-incrementally.md)」をご覧ください。|  
|.map|リンク|リンカー情報を含むテキスト ファイル。 マップ ファイルの名前は、[\/Fm](../Topic/-Fm%20\(Name%20Mapfile\).md) コンパイラ オプションで指定します。 詳細については、「[\/MAP](../build/reference/map-generate-mapfile.md)」を参照してください。|  
|.mfcribbon\-ms|リソース|リボンのボタン、コントロール、および属性を定義する XML コードを含むリソース ファイル。 詳細については、「[リボン デザイナー \(MFC\)](../mfc/ribbon-designer-mfc.md)」を参照してください。|  
|.obj、.o||オブジェクト ファイル。コンパイルはされますが、リンクはされません。|  
|.pch|デバッグ|プリコンパイル済みヘッダー ファイル。|  
|.rc、.rc2|リソース|リソースを生成するための[リソース スクリプト ファイル](../mfc/working-with-resource-files.md)。|  
|.sbr|コンパイル|ソース ブラウザー中間ファイル。[BSCMAKE](../Topic/BSCMAKE%20Options.md) の入力ファイルです。|  
|.sln|ソリューション|[ソリューション](http://msdn.microsoft.com/ja-jp/a45c299d-69f5-4b67-879d-1383417df0a7) ファイル。|  
|.suo|ソリューション|ソリューション オプション ファイル。|  
|.txt|リソース|テキスト ファイル。通常は README ファイルです。|  
|.vap|プロジェクト|Visual Studio Analyzer プロジェクト ファイル。|  
|.vbg|ソリューション|互換性のあるプロジェクト グループ ファイル。|  
|.vbp、.vip、.vbproj|プロジェクト|Visual Basic プロジェクト ファイル。|  
|.vcxproj|プロジェクト|Visual C\+\+ プロジェクト ファイル。 詳細については、「[プロジェクト ファイルとメイクファイル](../ide/project-and-solution-files.md)」を参照してください。|  
|.vcxproj.filters|プロジェクト|filters ファイルは、ソリューション エクスプローラーを使用してプロジェクトにファイルを追加するときに、ファイル名拡張子に基づいてソリューション エクスプローラーのツリー ビューでファイルを追加する場所を定義します。|  
|.vdproj|プロジェクト|Visual Studio 配置プロジェクト ファイル。|  
|.vmx|プロジェクト|マクロ プロジェクト ファイル。|  
|.vup|プロジェクト|ユーティリティ プロジェクト ファイル。|  
  
 Visual Studio に関連するその他のファイルの詳細については、「[Visual Studio .NET のファイルの種類と拡張子](../Topic/Project%20and%20Solution%20File%20Types.md)」を参照してください。  
  
 プロジェクト ファイルは、ソリューション エクスプローラーで複数のフォルダーに分けて編成されています。 Visual C\+\+ では、ソース ファイル、ヘッダー ファイル、およびリソース ファイル用のフォルダーが作成されます。これらのフォルダーを再編成したり、新しいフォルダーを作成したりできます。 フォルダーを使用すると、プロジェクト階層内で論理ファイル クラスターを明示的に編成できます。 たとえば、ユーザー インターフェイスのすべてのソース ファイル、仕様、ドキュメント、テスト スイートなどを格納するフォルダーを作成できます。 すべてのファイル フォルダーに一意の名前を指定する必要があります。  
  
 プロジェクトに項目を追加すると、その項目をビルドできるかどうかにかかわらず、プロジェクトのすべての構成にその項目が追加されます。 たとえば、MyProject というプロジェクトに項目を追加すると、プロジェクトのデバッグ構成とリリース構成の両方にその項目が追加されます。  
  
## 参照  
 [Visual C\+\+ プロジェクトの作成および管理](../ide/creating-and-managing-visual-cpp-projects.md)   
 [Visual C\+\+ プロジェクトの種類](../ide/visual-cpp-project-types.md)   
 [ウィザードでサポートされるその他の言語](../ide/wizard-support-for-other-languages.md)