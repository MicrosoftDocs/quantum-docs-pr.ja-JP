---
title: Q# コマンド ライン アプリケーションを使用した開発
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 4311ebf9f72254485a20ba721ea2ce19163f4371
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274124"
---
# <a name="develop-with-q-command-line-applications"></a>Q# コマンド ライン アプリケーションを使用した開発

Q# プログラムはそれ自体で実行可能です。C#、F#、Python などのホスト言語のドライバーは必要ありません。

## <a name="prerequisites"></a>前提条件

- [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

## <a name="installation"></a>インストール

Q# コマンド ライン アプリケーションはどんな IDE でもビルドできますが、Q# アプリケーションでは Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。 これらのツールで開発すると、豊富な機能を活用することができます。

VS Code を構成するには:

1. [VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をダウンロードしてインストールします。
2. [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) をインストールします。

Visual Studio を構成するには:

1. [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールし、.NET Core クロスプラットフォーム開発ワークロードを有効にします。
2. [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) をダウンロードしてインストールします。


## <a name="develop-with-q-using-vs-code"></a>VS Code を使用した Q# での開発

Q# プロジェクト テンプレートをインストールします。

1. VS Code を開きます。
2. **[表示]**  ->  **[コマンド パレット]** をクリックします。
3. **[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。

**[Project templates installed successfully]\(プロジェクト テンプレートが正常にインストールされました\)** と表示されたら、QDK を自分のアプリケーションとライブラリで使用することができます。

新しいプロジェクトを作成するには:

1. **[表示]**  ->  **[コマンド パレット]** をクリックして、 **[Q#:新しいプロジェクトの作成]** を選択します。
2. **[Standalone console application]\(スタンドアロン コンソール アプリケーション\)** をクリックします。
3. プロジェクトを保存する場所に移動して、 **[プロジェクトの作成]** をクリックします。
4. プロジェクトが正常に作成されたら、右下にある **[Open new project...]\(新しいプロジェクトを開く...\)** をクリックします。
        
プロジェクトを確認します。 `Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。

アプリケーションを実行するには:
1. **[ターミナル]**  ->  **[新しいターミナル]** をクリックします。
2. ターミナル プロンプトで、`dotnet run` と入力します。
3. 出力ウィンドウに `Hello quantum world!` というテキストが表示されます。


> [!NOTE]
> 複数のルート フォルダーを持つワークスペースは、VS Code の Q# 拡張機能では現在サポートされていません。 1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。

## <a name="develop-with-q-using-visual-studio"></a>Visual Studio を使用した Q# での開発

Q# の `Hello World` アプリケーションを作成して、Visual Studio のインストールを確認します。

新しい Q# アプリケーションを作成するには:
1. Visual Studio を開き、 **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** をクリックします。
2. 検索ボックスに `Q#` と入力し、 **[Q# アプリケーション]** を選択して **[次へ]** をクリックします。
3. アプリケーションの名前と場所を入力して、 **[作成]** をクリックします。


プロジェクトを確認します。 `Program.qs` という名前のソース ファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。

アプリケーションを実行するには:
1. **[デバッグ]**  ->  **[デバッグなしで開始]** を選択します。
2. テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。

> [!NOTE]
> 1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。  


## <a name="next-steps"></a>次のステップ

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。
