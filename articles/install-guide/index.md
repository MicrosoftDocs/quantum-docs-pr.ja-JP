---
title: Microsoft Quantum Development Kit (QDK) をインストールする方法について
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install
ms.openlocfilehash: 090cf98612c6c549c733e54f9dcbf74442b30fbd
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442265"
---
# <a name="install-the-microsoft-quantum-development-kit-qdk"></a>Microsoft Quantum Development Kit (QDK) のインストール

Microsoft Quantum Development Kit (QDK) をインストールする方法について説明します。これにより、量子プログラミングを始めることができます。 QDK は次の要素で構成されます。

- Q# プログラミング言語
- Q# の複雑な機能を抽象化するライブラリのセット
- Q# で記述された量子操作を実行するホスト アプリケーション (Python または .NET 言語で記述)
- 開発を容易にするツール

選択した開発環境に応じて、さまざまなインストール手順があります。 以下のセクションから環境を選択してください。

## <a name="develop-with-python"></a>Python を使用した開発

Python 用の qsharp パッケージを使用すると、Python 内から Q# の演算と関数を簡単にシミュレートできます。 IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。

1. 前提条件

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー
    - [.NET Core SDK 3.0 以降](https://www.microsoft.com/net/download)

1. `iqsharp` パッケージのインストール

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `qsharp` パッケージのインストール

    ```bash
    pip install qsharp
    ```

1. `Hello World` アプリケーションを作成してインストールを確認する

    - `Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。

        ```qsharp
        namespace HelloWorld
        {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Result {
                Message("Hello from quantum world!");
                return Zero;
            }
        }
        ```

    - Q# `SayHello()` 操作を呼び出す `hello_world.py` という名前の Python プログラムを作成します。

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - 以下のプログラムを実行します。

        ```bash
        python hello_world.py
        ```

    - 出力を検証します。 プログラムから次の行が出力されます。

        ```bash
        Hello from quantum world!
       0
       ```

## <a name="develop-with-jupyter-notebooks"></a>Jupyter Notebook を使用した開発

教育機関向けの設定、科学的研究所、およびオンラインベースのコラボレーション プログラミングで好まれる Jupyter Notebook では、命令、メモ、その他のコンテンツと共に、Q# コードを含むインプレース コード実行が提供されるようになりました。  独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。

IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。


1. 前提条件

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.0 以降](https://www.microsoft.com/net/download)

1. `iqsharp` パッケージのインストール

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 次のコマンドを実行して、Notebook サーバーを起動します。

        ```bash
        jupyter notebook
        ```

    - コマンド ラインに表示されている URL を参照します。 例: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

    - Q# カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Notebook のこのセルを実行します。

        ![Q# コードを含む Jupyter Notebook セル](~/media/install-guide-jupyter.png)

        セルの出力に `SayHello` が表示されます。 Jupyter Notebook で実行すると、Q# コードがコンパイルされ、ノートブックから検出した操作の名前が出力されます。


    - 新しいセルで、`%simulate` マジックを使用して、作成した演算の量子コンピューターでの実行をシミュレートします。

        ![%simulate マジックのある Jupyter Notebook セル](~/media/install-guide-jupyter-simulate.png)

        呼び出した演算の結果 (この場合は空) と共に、メッセージが画面に表示されます。


## <a name="develop-with-c-on-windows-using-visual-studio"></a>Visual Studio を使用した Windows での C# の開発

Visual Studio には、開発者がアプリケーションを構築する際にガイドするコード補完や構文の強調表示などの優れた機能が用意されており、Q# プログラムの充実した環境を提供します。  Q# Visual Studio 拡張機能には、構文の強調表示や IntelliSense のサポートに加えて、Q# のファイルおよびプロジェクトのテンプレートが含まれます。


1. 前提条件

    - .NET Core クロス プラットフォーム開発ワークロードが有効な [Visual Studio](https://visualstudio.microsoft.com/downloads/) 16.3

1. Q# Visual Studio 拡張機能のインストール

    - [Visual Studio 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.DevKit)をダウンロードする
    - 拡張機能を Visual Studio に追加する

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 新しい Q# アプリケーションを作成する

        - **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。
        - 検索ボックスに、「`Q#`」と入力します
        - **[Q# Application]\(Q# アプリケーション\)** を選択します
        - **[次へ]** を選択します
        - アプリケーションの名前と格納する場所を選択します
        - **[作成]**

    - プロジェクトの確認

        2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。

    - アプリケーションの実行

        - **[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。
        - テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。

> [!NOTE]
> * 1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。  

## <a name="develop-with-c-using-visual-studio-code"></a>Visual Studio Code を使用した C# での開発

Visual Studio Code (VS Code) には、開発者がアプリケーションを構築する際にガイドするコード補完や構文の強調表示などの優れた機能が用意されており、Windows、Linux、Mac などの複数のコンピューター環境にわたって Q# プログラムの開発用の充実した環境を提供します。  Q# VS Code 拡張機能には、構文の強調表示と Q# コード スニペットが含まれています。

Visual Studio Code (VS Code) には、開発者がアプリケーションを構築する際にガイドするコード補完や構文の強調表示などの優れた機能が用意されており、Windows、Linux、Mac などの複数のコンピューター環境にわたって Q# プログラムの開発用の充実した環境を提供します。  Q# VS Code 拡張機能には、構文の強調表示と Q# コード スニペットが含まれています。

1. 前提条件

   - [VS Code](https://code.visualstudio.com/download)
   - [.NET Core SDK 3.0 以降](https://www.microsoft.com/net/download)

1. Quantum VS Code 拡張機能のインストール

    - [VS Code 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールする

1. 量子プロジェクト テンプレートをインストールします。

   - **[表示]**  ->  **[コマンド パレット]** の順に選択します。
   - **[Q#:Install project templates]\(Q#: プロジェクト テンプレートのインストール\)** を選択します。

    これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 新しいプロジェクトを作成します。

        - **[表示]**  ->  **[コマンド パレット]** の順に選択します。
        - **[Q#:Create New Project]\(新しいプロジェクトの作成\)** を選択します。
        - アプリケーションの作成先となるファイル システム上の場所に移動します。
        - プロジェクトが作成されたら、 **[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。

    - アプリケーションを実行します。

        - **[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。
        - 出力ウィンドウに `Hello quantum world!` というテキストが表示されます。

> [!NOTE]
> * > * 複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。 1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。

## <a name="develop-with-c-using-the-dotnet-command-line-tool"></a>`dotnet` コマンド ライン ツールを使用した C# での開発

もちろん、単に .NET Core SDK と QDK プロジェクト テンプレートをインストールして、コマンド ラインから Q# プログラムを構築して実行することもできます。 

1. 前提条件

    - [.NET Core SDK 3.0 以降](https://www.microsoft.com/net/download)

1. .NET 用量子プロジェクト テンプレートをインストールします。

    ```bash
    dotnet new -i Microsoft.Quantum.ProjectTemplates
    ```

    これで、Quantum Development Kit がインストールされ、使用しているアプリケーションとライブラリで使用できるようになりました。

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 新しいアプリケーションを作成する

       ```bash
       dotnet new console -lang Q# -o runSayHello
       ```

    - 新しいアプリケーション ディレクトリに移動します。

       ```bash
       cd runSayHello
       ```

    アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。

    - アプリケーションの実行

        ```bash
        dotnet run
        ```

        `Hello quantum world!` という出力が表示されます。

## <a name="whats-next"></a>次の手順

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。
