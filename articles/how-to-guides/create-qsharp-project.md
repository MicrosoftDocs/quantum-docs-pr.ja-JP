---
title: 'Quantum Development Kit (QDK) を使用して Q # プロジェクトを作成する方法について説明します。'
description: '選択した開発環境の QDK と Q # を使用して、quantum 開発用のプロジェクトを初期化します'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 5fa32f14291fa2070b49e4bb3b720cbf31ee614b
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819894"
---
# <a name="create-a-q-project-in-your-development-environment"></a>開発環境で Q # プロジェクトを作成する

QDK で Q # プロジェクトを作成する方法について説明します。

Q # プロジェクトには、クォンタムコードを含む Q # ファイルと、クォンタムプログラムを実行するホストプログラムが含まれています。 ホストプログラムはC#、や Python などの .net 言語で記述できます。 また、IQ # kernel を使用して、Jupyter notebook で Q # コードを実行することもできます。

以下のセクションで、開発環境と言語を選択します。

* [Python](#create-a-python-project)
* [Q # Jupyter notebook](#create-a-q-jupyter-notebook-project)
* [C#Visual Studio を使用する](#create-a-c-project-on-windows-using-visual-studio)
* [C#VS Code](#create-a-c-project-using-vs-code)
* [C#コマンドラインを使用する](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Python プロジェクトを作成する

1. 前提条件

     * [Python 用 Quantum 開発キット](xref:microsoft.quantum.install.python)をインストールする

1. プロジェクトのフォルダーを作成し、そのフォルダーに移動します。

1. `Operation.qs`という名前の Q # ファイルを作成し、そのファイルに Q # コードを追加します。 例えば次が挙げられます。

    ```qsharp
    namespace HelloWorld {
        open Microsoft.Quantum.Intrinsic;
        open Microsoft.Quantum.Canon;

        operation SayHello() : Result {
            Message("Hello from quantum world!");
            return Zero;
        }
    }
    ```

1. Q # 操作を呼び出すために `host.py` という名前の python ホストファイルを作成します。 例えば次が挙げられます。

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. 以下のプログラムを実行します。

    ```bash
    python host.py
    ```

1. 出力を検証します。 プログラムから次の行が出力されます。

    ```bash
    Hello from quantum world!
    0
    ```

これで、quantum プログラムの開発を続けることができます。

## <a name="create-a-q-jupyter-notebook-project"></a>Q # Jupyter Notebook プロジェクトを作成する

1. 前提条件

    * [Jupyter notebook 用の Quantum 開発キットを](xref:microsoft.quantum.install.jupyter)インストールする

1. 次のコマンドを実行して、Notebook サーバーを起動します。

    ```bash
    jupyter notebook
    ```

1. コマンド ラインに表示されている URL を参照します。 例: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85 ]

1. Jupyter ページがブラウザーに表示されます。 **[ファイル]** タブで [**新規** > **q #** ] を選択し、q # カーネルで jupyter notebook を作成します。 最初の notebook セルに次のコードを追加します。

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. [セル]**を選択**して [ > ] を**選択し、** notebook を実行します。 `SayHello` は、すぐにセルの出力に表示されます。

    ![Q# コードを含む Jupyter Notebook セル](~/media/install-guide-jupyter.png)

    Jupyter Notebook で実行すると、Q # コードがコンパイルされ、ノートブックは検出した操作の名前を出力します。

1. 新しいセルで、`%simulate` マジックを使用して、作成した演算の量子コンピューターでの実行をシミュレートします。

    ![%simulate マジックのある Jupyter Notebook セル](~/media/install-guide-jupyter-simulate.png)

    呼び出した演算の結果 (この場合は空) と共に、メッセージが画面に表示されます。

他の Q # 操作を追加して、量子開発を続けることができるようになりました。

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Visual Studio C#を使用した Windows でのプロジェクトの作成

1. 前提条件

    * [Visual Studio 用の Quantum Development Kit 拡張機能](xref:microsoft.quantum.install.cs)をインストールする

1. 新しい Q# アプリケーションを作成する

    * **[ファイル]**  ->  **[新規]**  ->  **[プロジェクト]** の順に移動します。
    * 検索ボックスに、「`Q#`」と入力します
    * **[Q# Application]\(Q# アプリケーション\)** を選択します
    * **[次へ]** を選択します
    * アプリケーションの名前と格納する場所を選択します
    * **[作成]**

1. プロジェクトの確認

    2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。

1. アプリケーションの実行

    * **[デバッグ]**  ->  **[デバッグなしで開始]** の順に選択します。
    * テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。

Visual Studio を使用して、量子開発を続けることができるようになりました。

> [!NOTE]
> * 1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。  

## <a name="create-a-c-project-using-vs-code"></a>VS Code をC#使用してプロジェクトを作成する

1. 前提条件

    * [VS Code 用の Quantum Development Kit 拡張機能](xref:microsoft.quantum.install.cs)をインストールする

1. 新しいプロジェクトを作成します。

    * **[表示]**  ->  **[コマンド パレット]** の順に選択します。
    * **[Q #: 新しいプロジェクトの作成]** を選択します。
    * **スタンドアロンコンソールアプリケーション**の選択
    * アプリケーションの作成先となるファイル システム上の場所に移動します。
    * プロジェクトが作成されたら、 **[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。

1. アプリケーションを実行します。

    * **ターミナル** -> **新しいターミナル**にアクセスする
    * 「`dotnet run`」と入力します
    * 出力ウィンドウに `Hello quantum world!` というテキストが表示されます。

Visual Studio Code を使用して、quantum の開発を続けることができるようになりました。

> [!NOTE]
> * 複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。 1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>`dotnet` コマンドC#ラインツールを使用してプロジェクトを作成する

1. 前提条件

    * [コマンドライン用の Quantum 開発キット](xref:microsoft.quantum.install.cs)をインストールする

1. 新しいアプリケーションを作成する

    ```bash
    dotnet new console -lang Q# -o <project name>
    ```

1. 新しいアプリケーション ディレクトリに移動します。

    ```bash
    cd <project name>
    ```

    アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。

1. アプリケーションの実行

    ```bash
    dotnet run
    ```

    `Hello quantum world!` という出力が表示されます。

これで、コマンドラインツールを使用して、クォンタム開発を続行できます。

## <a name="whats-next"></a>次に、

お好みの環境でプロジェクトを作成したので、量子開発を続けることができます。
