---
title: Q# コマンド ライン アプリケーションを使用した開発
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 3d70838289e72afdd0a48bbdff0bec407428d125
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871435"
---
# <a name="develop-with-q-command-line-applications"></a>Q# コマンド ライン アプリケーションを使用した開発

Q# プログラムはそれ自体で実行可能です。C#、F#、Python などのホスト言語のドライバーは必要ありません。

## <a name="prerequisites"></a>前提条件

- [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

## <a name="installation"></a>インストール

Q# コマンド ライン アプリケーションはどの IDE でもビルドできますが、Q# アプリケーションをローカルで開発する場合は Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。 Web ブラウザーを使用してクラウドで開発する場合は、Visual Studio Codespaces をお勧めします。 これらの環境での開発には、警告、構文の強調表示、プロジェクト テンプレートなど、QDK 拡張機能の豊富な機能が用意されています。 

VS Code を構成するには:

1. [VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をダウンロードしてインストールします。
2. [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) をインストールします。

Visual Studio を構成するには:

1. [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールし、.NET Core クロスプラットフォーム開発ワークロードを有効にします。
2. [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) をダウンロードしてインストールします。

Visual Studio Codespaces を構成するには:

1. [Azure アカウント](https://azure.microsoft.com/free/)を作成します。
2. Codespaces 環境を作成します。 [クイックスタート ガイド](https://docs.microsoft.com/visualstudio/online/quickstarts/browser)に従ってください。 Codespace を作成するときに、[Git リポジトリ] フィールドに「`microsoft/Quantum`」と入力して、QDK 固有の設定を読み込むことをお勧めします。
3. これで、新しい環境を起動し、[VS Codespaces のクラウド IDE](https://online.visualstudio.com/environments) を使用してブラウザーで開発を開始できるようになりました。 または、VS Code のローカル インストールを使用して、[リモート環境](https://docs.microsoft.com/visualstudio/online/how-to/vscode)として Codespaces を使用することもできます。


別の環境の QDK をインストールするには、コマンド ラインで次のように入力します。

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Q# を使用した開発

お使いの環境に対応するタブの指示に従ってください。

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

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

### <a name="visual-studio"></a>[Visual Studio](#tab/tabid-vs)

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

### <a name="other-editors-with-the-command-line"></a>[コマンド ラインを使用した他のエディター](#tab/tabid-cmdline)

Q# の `Hello World` アプリケーションを作成して、インストールを確認します。

1. プロジェクト テンプレートをインストールします。

    ```dotnetcli
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

1. 新しいアプリケーションを作成します。
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

1. アプリケーション ディレクトリに移動します。
    ```dotnetcli
    cd runSayHello
    ```

    このディレクトリには `Program.qs` という名前のファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。 このテンプレートをテキスト エディターで変更し、独自のクォンタム アプリケーションで上書きすることができます。 

1. 以下のプログラムを実行します。
    ```dotnetcli
    dotnet run
    ```

1. 次のように表示されます。`Hello quantum world!`

***

## <a name="next-steps"></a>次のステップ

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。
