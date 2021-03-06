---
title: "手順 1 - C++ コンソール アプリケーション プロジェクトを作成 |Microsoft ドキュメント"
description: "Visual Studio の Visual C サポートをインストールします。"
ms.custom: mvc
ms.date: 10/17/2017
ms.topic: get-started-article
ms.technology: devlang-C++
ms.devlang: C++
dev_langs: C++
ms.assetid: 45138d70-719d-42dc-90d7-1d0ca31a2f54
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f75d8fc6ec744038d57bfb7576547c9be84b7551
ms.sourcegitcommit: 69632887f7a85f4841c49b4c1353d3144927a52c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2017
---
# <a name="create-a-c-console-app-project"></a>C++ コンソール アプリケーション プロジェクトを作成します。

通常の始点 C++ プログラマが、「こんにちは, world!」 コマンドラインで実行されるアプリケーションです。 新機能を作成する Visual Studio でこのステップでです。

## <a name="prerequisites"></a>必須コンポーネント

- インストールされているし、コンピューターで実行されている C++ ワークロードでデスクトップの開発に Visual Studio があります。 場合はそれがまだインストールされていないを参照してください。[ステップ 0 - Visual Studio での C++ のインストール サポート](../build/vscpp-step-0-installation.md)です。

## <a name="create-your-app-project"></a>アプリ プロジェクトを作成します。

Visual Studio を使用して*プロジェクト*、アプリのコードを整理して*ソリューション*プロジェクトを整理します。 プロジェクトでは、すべてのオプション、構成、および、アプリをビルドするための規則が含まれていて、プロジェクトのすべてのファイルと、外部のファイル間のリレーションシップを管理します。 アプリを作成するに最初を作成する新しいプロジェクトとソリューションです。

1. Visual Studio で開く、**ファイル**メニューを選択し、**新規 > プロジェクト**を開くには、**新しいプロジェクト**ダイアログ。

   ![新しいプロジェクト ダイアログを開く](../build/media/vscpp-file-new-project.gif "新しいプロジェクト ダイアログを開く")

1. **新しいプロジェクト**ダイアログで、**インストール**、 **Visual C**順に選択が既に選択されていない場合、**空のプロジェクト**テンプレートです。 **名前**フィールドに「 *HelloWorld*です。 選択**OK**プロジェクトを作成します。

   ![名前を指定し、新しいプロジェクトを作成する](../build/media/vscpp-concierge-project-name-callouts.png "名および新しいプロジェクトの作成")

Visual Studio では、新しい、空プロジェクトを作成して、ソース コード ファイルに追加するアプリの種類の特殊化するための準備ができてを作成します。 次を行います。

[問題が発生しました。](#create-your-app-project-issues)

## <a name="make-your-project-a-console-app"></a>コンソール アプリ プロジェクトを作成します。

Visual Studio では、Windows およびその他のプラットフォーム用アプリとコンポーネントのすべての種類を作成できます。 **空のプロジェクト**テンプレートいないどのような種類のアプリの作成について説明します。 作成する、*コンソール アプリ*1 つ、コンソールまたはコマンド プロンプト ウィンドウで実行すると、Visual Studio からコンソール サブシステムを使用してアプリをビルドを指定する必要があります。

1. Visual Studio で開く、**プロジェクト**メニューを選択し、**プロパティ**を開くには、 **HelloWorld プロパティ ページ**ダイアログ。

1. **プロパティ ページ**ダイアログ **構成プロパティ****リンカー**、**システム**、横に、編集ボックスをクリックし、**サブシステム**プロパティです。 表示されるドロップダウン メニューで、選択**コンソール (/サブシステム: コンソール)**です。 選択**OK**して変更を保存します。

   ![プロパティ ページ ダイアログを開く](../build/media/vscpp-properties-linker-subsystem.gif "プロパティ ページ ダイアログを開く")

Visual Studio は、プロジェクトをビルドして、コンソール ウィンドウで実行するようになりました認識します。 次に、ソース コード ファイルを追加し、アプリのコードを入力します。

[問題が発生しました。](#make-your-project-a-console-app-issues)

## <a name="add-a-source-code-file"></a>ソース コード ファイルを追加します。

1. **ソリューション エクスプ ローラー**、HelloWorld プロジェクトを選択します。 メニュー バーで、次のように選択します。**プロジェクト**、**新しい項目の追加**を開くには、**新しい項目の追加**ダイアログ。

1. **新しい項目の追加**ダイアログで、 **Visual C** **インストール**既に選択されていない場合。 中央のウィンドウで次のように選択します。 **C++ ファイル (.cpp)**です。 変更、**名前**に*HelloWorld.cpp*です。 選択**追加**をダイアログ ボックスを閉じて、ファイルを作成します。

   ![HelloWorld.cpp のソース ファイルを追加](../build/media/vscpp-add-new-item.gif "HelloWorld.cpp のソース ファイルを追加")

Visual studio では、新しい、空のソース コード ファイルが作成され、ソース コードを入力する準備がエディター ウィンドウで開かれます。

[問題が発生しました。](#add-a-source-code-file-issues)

## <a name="add-code-to-the-source-file"></a>ソース ファイルにコードを追加します。

1. このコードを HelloWorld.cpp エディター ウィンドウにコピーします。

   ```cpp
   #include <iostream>

   int main()
   {
       std::cout << "Hello, world!" << std::endl;
       return 0;
   }
   ```

   コードをエディター ウィンドウで次のようになります。

   ![Hello World コード エディターで](../build/media/vscpp-hello-world-editor.png "エディターでの Hello World コード")

コードは、エディターで次のようになっているは、次の手順に進んでくださいし、アプリをビルドする準備ができたらです。

[問題が発生しました。](#add-a-source-code-file-issues)

## <a name="next-steps"></a>次の手順

> [!div class="nextstepaction"]
> [手順 2: ビルドし、C++ プロジェクトを実行](vscpp-step-2-build.md)

## <a name="troubleshooting-guide"></a>トラブルシューティング ガイド

ここでソリューションの一般的な問題時になる最初の C++ プロジェクトを作成します。

### <a name="create-your-app-project-issues"></a>アプリ プロジェクトの懸案事項を作成します。

場合、**新しいプロジェクト**ダイアログが表示されない、 **Visual C**エントリ**インストール**、Visual Studio のコピーはおそらくありません、**デスクトップC++ を使用した開発**ワークロードがインストールされています。 右からインストーラーを実行することができます、**新しいプロジェクト**ダイアログ。 選択、**開いている Visual Studio インストーラー**インストーラーをもう一度起動するリンクです。 場合、**ユーザー アカウント制御**ダイアログのアクセス許可を要求する、選択**はい**です。 Installer で、確認、 **C++ を使用したデスクトップ開発**ワークロードが確認され、選択**[ok]**を Visual Studio のインストールを更新します。

同じ名前の別のプロジェクトが既に存在する場合、プロジェクトの別の名前を選択または既存のプロジェクトの削除し、もう一度やり直してください。 既存のプロジェクトを削除するには、ファイル エクスプ ローラーでソリューション フォルダー (helloworld.sln ファイルが含まれているフォルダー) を削除します。

[戻る](#create-your-app-project)です。

### <a name="make-your-project-a-console-app-issues"></a>コンソール アプリに関する問題、プロジェクトを作成します。

表示されない場合**リンカー**下に表示**構成プロパティ**、選択**キャンセル**を閉じる、**プロパティ ページ**ダイアログし、確認して、 **HelloWorld**でプロジェクトを選択**ソリューション エクスプ ローラー**、いない、ソリューションまたは別のファイルまたはフォルダーを再実行する前にします。

ドロップダウン コントロールがない、**サブシステム**プロパティがプロパティを選択するまで、ボックスを編集します。 で、ポインターを使用して選択できますかまでダイアログ コントロールを順番に tab**サブシステム**が強調表示されます。 ドロップダウン コントロールを選択するか、Alt + Down を開くには、キーを押します。

[戻ってください](#make-your-project-a-console-app)

### <a name="add-a-source-code-file-issues"></a>ソース コード ファイルの問題を追加します。

ソース コード ファイルに別の名前を付ける場合は問題ありません。 ただし、同じプロジェクトにコードを含む 1 つ以上のソース コード ファイルを追加しません。

間違った種類のファイルをプロジェクトに追加する場合など、ヘッダー ファイルは削除し、もう一度やり直してください。 ファイルを削除するで選択して**ソリューション エクスプ ローラー** Del キーを押します。

[戻る](#add-a-source-code-file)です。

### <a name="add-code-to-the-source-file-issues"></a>ソース ファイルの問題にコードを追加します。

ソース コード ファイル エディター ウィンドウをもう一度開くを誤って閉じた場合で HelloWorld.cpp をダブルクリック、**ソリューション エクスプ ローラー**ウィンドウです。

ソース コード エディターでは何も下にある赤い波線が表示されない場合は、コードの例では、スペル、句読点、および大文字小文字と一致していることを確認します。 場合は、C++ コードで重要です。

[戻る](#add-code-to-the-source-file)です。

<iframe src="" height="0" width="0" frameborder="0" name="frameTarget" />