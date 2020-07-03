---
title: Q# コマンド ライン アプリケーションを使用した開発
author: KittyYeungQ
ms.author: kitty
ms.date: 4/24/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.standalone
ms.openlocfilehash: 15015d1673f47faf5a13dde516f834916b4319d6
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884285"
---
# <a name="develop-with-q-command-line-applications"></a>Q# コマンド ライン アプリケーションを使用した開発

Q# プログラムはそれ自体で実行可能です。C#、F#、Python などのホスト言語のドライバーは必要ありません。

## <a name="prerequisites"></a>前提条件

- [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

## <a name="installation"></a>インストール

Q# コマンド ライン アプリケーションはどんな IDE でもビルドできますが、Q# アプリケーションでは Visual Studio Code (VS Code) または Visual Studio IDE を使用することをお勧めします。 これらの環境での開発には、警告、構文の強調表示、プロジェクト テンプレートなど、QDK 拡張機能の豊富な機能が用意されています。

VS Code を構成するには:

1. [VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をダウンロードしてインストールします。
2. [Microsoft QDK for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode) をインストールします。

Visual Studio を構成するには:

1. [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3 以降をダウンロードしてインストールし、.NET Core クロスプラットフォーム開発ワークロードを有効にします。
2. [Microsoft QDK](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit) をダウンロードしてインストールします。

別の環境の QDK をインストールするには、コマンド ラインで次のように入力します。

```dotnetcli
dotnet new -i Microsoft.Quantum.ProjectTemplates
```

## <a name="develop-with-q"></a>Q# を使用した開発

お使いの環境に対応するタブの指示に従ってください。

### <a name="vs-code"></a>[VS Code](#tab/tabid-vscode)

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

1. 新しいアプリケーションを作成します。
    ```dotnetcli
    dotnet new console -lang Q# -o runSayHello
    ```

2. アプリケーション ディレクトリに移動します。
    ```dotnetcli
    cd runSayHello
    ```

    このディレクトリには `Program.qs` という名前のファイルがあるはずです。これは、コンソールにメッセージを表示する簡単な演算を定義する Q# プログラムです。 このテンプレートをテキスト エディターで変更し、独自のクォンタム アプリケーションで上書きすることができます。 

3. 以下のプログラムを実行します。
    ```dotnetcli
    dotnet run
    ```

4. 次のように表示されます。`Hello quantum world!`

***

## <a name="next-steps"></a>次のステップ

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。
