---
title: 'Q # コマンドラインアプリケーションを使用した開発'
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630274"
---
# <a name="develop-with-q-command-line-applications"></a>Q # コマンドラインアプリケーションを使用した開発

Q # プログラムは、C#、F #、Python などのホスト言語でドライバーを使用しなくても、独自に実行できます。

## <a name="prerequisites"></a>前提条件

- [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

## <a name="installation"></a>インストール

任意の IDE で Q # コマンドラインアプリケーションをビルドできますが、Q # アプリケーションには Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。 これらのツールで開発することで、豊富な機能にアクセスできます。

VS Code を構成するには:

1. [VS Code](https://code.visualstudio.com/download) (Windows、Linux、および Mac) をダウンロードしてインストールします。
2. [Microsoft QDK for VS Code を](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)インストールします。

Visual Studio を構成するには:

1. .NET Core クロスプラットフォームの開発ワークロードが有効になっている[Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールします。
2. [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードしてインストールします。


## <a name="develop-with-q-using-vs-code"></a>VS Code を使用した Q # での開発

Q # プロジェクトテンプレートをインストールします。

1. VS Code を開きます。
2. [ **View**  ->  **コマンドパレット**の表示] をクリックします。
3. [ **Q #: Install project templates**] を選択します。

**プロジェクトテンプレートが正常にインストール**されると、qdk を独自のアプリケーションやライブラリで使用する準備が整います。

新しいプロジェクトを作成するには:

1. [ **View**  ->  **コマンドパレット**の表示] をクリックし、[ **Q #: 新しいプロジェクトの作成**] を選択します。
2. [**スタンドアロンコンソールアプリケーション**] をクリックします。
3. プロジェクトを保存する場所に移動し、[**プロジェクトの作成**] をクリックします。
4. プロジェクトが正常に作成されたら、右下にある [**新しいプロジェクトを開く**] をクリックします。
        
プロジェクトを検査します。 という名前のソースファイルが表示 `Program.qs` されます。これは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。

アプリケーションを実行するには:
1. [**ターミナル**  ->  の**新しいターミナル**] をクリックします。
2. ターミナルプロンプトで、「」と入力し `dotnet run` ます。
3. 出力ウィンドウに `Hello quantum world!` というテキストが表示されます。


> [!NOTE]
> 複数のルートフォルダーを持つワークスペースは、現在 VS Code Q # 拡張機能ではサポートされていません。 1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。

## <a name="develop-with-q-using-visual-studio"></a>Visual Studio を使用した Q # での開発

Q # アプリケーションを作成して、Visual Studio のインストールを確認し `Hello World` ます。

新しい Q # アプリケーションを作成するには:
1. Visual Studio を開き、[**ファイル**] [  ->  **新しい**  ->  **プロジェクト**] の順にクリックします。
2. `Q#`検索ボックスに「」と入力し、[ **Q # アプリケーション**] を選択して、[**次へ**] をクリックします。
3. アプリケーションの名前と場所を入力し、[**作成**] をクリックします。


プロジェクトを検査します。 という名前のソースファイルが表示 `Program.qs` されます。これは、コンソールにメッセージを出力する簡単な操作を定義する Q # プログラムです。

アプリケーションを実行するには:
1. [**デバッグ**] [  ->  **デバッグなしで開始**] を選択します。
2. テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。

> [!NOTE]
> 1つの Visual Studio ソリューション内に複数のプロジェクトがある場合、ソリューションに含まれるすべてのプロジェクトは、ソリューションと同じフォルダー、またはそのサブフォルダーの1つに存在する必要があります。  


## <a name="next-steps"></a>次のステップ

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。
