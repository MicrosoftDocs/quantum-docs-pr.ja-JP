---
title: 'Quantum Development Kit (QDK) を使用して Q # プロジェクトを作成する方法について説明します。'
description: '選択した開発環境の QDK と Q # を使用して、quantum 開発用のプロジェクトを初期化します'
author: natke
ms.author: nakersha
ms.date: 10/19/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.howto.createproject
ms.openlocfilehash: 8af8e3288aab731520ede984d5f89644de292385
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578213"
---
# <a name="create-a-q-project-in-your-development-environment"></a>開発環境で Q # プロジェクトを作成する

QDK で Q # プロジェクトを作成する方法について説明します。

Q # プロジェクトには、クォンタムコードを含む Q # ファイルと、クォンタムプログラムを実行するホストプログラムが含まれています。 ホストプログラムは、C# などの .NET 言語、または Python で記述できます。 また、IQ # kernel を使用して Jupyter Notebook で Q # コードを実行することもできます。

以下のセクションで、開発環境と言語を選択します。

* [Python](#create-a-python-project)
* [Q# Jupyter Notebook](#create-a-q-jupyter-notebook-project)
* [Visual Studio を使用した C#](#create-a-c-project-on-windows-using-visual-studio)
* [VS Code を使用した C#](#create-a-c-project-using-vs-code)
* [コマンドラインを使用した C#](#create-a-c-project-using-the-dotnet-command-line-tool)

## <a name="create-a-python-project"></a>Python プロジェクトの作成

1. 前提条件

     * [Python 用 Quantum 開発キット](xref:microsoft.quantum.install.python)をインストールする

1. プロジェクトのフォルダーを作成し、そのフォルダーに移動します。

1. という名前の Q # ファイルを作成 `Operation.qs` し、そのファイルに q # コードを追加します。 次に例を示します。

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

1. という名前の python ホストファイルを作成し、 `host.py` Q # 操作を呼び出します。 次に例を示します。

    ```python
    import qsharp

    from HelloWorld import SayHello

    SayHello.simulate()
    ```

1. 以下のプログラムを実行します。

    ```
    python host.py
    ```

1. 出力を検証します。 プログラムから次の行が出力されます。

    ```
    Hello from quantum world!
    0
    ```

これで、quantum プログラムの開発を続けることができます。

## <a name="create-a-q-jupyter-notebook-project"></a>Q # Jupyter Notebook プロジェクトを作成する

1. 前提条件

    * [Jupyter notebook 用の Quantum 開発キットを](xref:microsoft.quantum.install.jupyter)インストールする

1. 次のコマンドを実行して、Notebook サーバーを起動します。

    ```
    jupyter notebook
    ```

1. コマンド ラインに表示されている URL を参照します。 例: [http://localhost:8888/?token=c790a52ba54f0cf77465c3c8983d776348285b0280d91b85]

1. Jupyter ページがブラウザーに表示されます。 [**ファイル**] タブで [**新しい**q #] を選択し、  >  **Q#** q # カーネルを使用して Jupyter Notebook を作成します。 最初の notebook セルに次のコードを追加します。

    ```qsharp
    operation SayHello() : Unit {
        Message("Hello from quantum world!");
    }
    ```

1. [**セル**の実行] [セル] を選択し  >  **Run Cells**て、notebook を実行します。 `SayHello`は、すぐにセルの出力に表示されます。

    ![Q # コードを含むセルを Jupyter Notebook](~/media/install-guide-jupyter.png)

    Jupyter Notebook で実行すると、Q # コードがコンパイルされ、ノートブックは検出した操作の名前を出力します。

1. 新しいセルで、`%simulate` マジックを使用して、作成した演算の量子コンピューターでの実行をシミュレートします。

    ![% シミュレートマジックを含むセルを Jupyter Notebook](~/media/install-guide-jupyter-simulate.png)

    呼び出した演算の結果 (この場合は空) と共に、メッセージが画面に表示されます。

他の Q # 操作を追加して、量子開発を続けることができるようになりました。

## <a name="create-a-c-project-on-windows-using-visual-studio"></a>Visual Studio を使用した Windows での C# プロジェクトの作成

1. 前提条件

    * [Visual Studio 用の Quantum Development Kit 拡張機能](xref:microsoft.quantum.install.cs)をインストールする

1. 新しい Q# アプリケーションを作成する

    * ファイルの**File**  ->  **新しい**  ->  **プロジェクト**にアクセス
    * 検索ボックスに、「`Q#`」と入力します
    * **[Q# Application]\(Q# アプリケーション\)** を選択します
    * **[次へ]** を選択します
    * アプリケーションの名前と格納する場所を選択します
    * **[作成]**

1. プロジェクトの確認

    2 つのファイルが作成されていることがわかります。`Driver.cs` は C# ホスト アプリケーションで、`Operation.qs` は、コンソールにメッセージを出力する簡単な操作を定義する Q# プログラムです。

1. アプリケーションの実行

    * デバッグ**Debug**を  ->  **行わないデバッグ開始**の選択
    * テキスト `Hello quantum world!` がコンソール ウィンドウに出力されます。

Visual Studio を使用して、量子開発を続けることができるようになりました。

> [!NOTE]
> * 1 つの Visual Studio ソリューションに複数のプロジェクトがある場合は、ソリューションに含まれるすべてのプロジェクトが、ソリューションと同じフォルダーまたはそのサブフォルダーのいずれかに存在する必要があります。  

## <a name="create-a-c-project-using-vs-code"></a>VS Code を使用して C# プロジェクトを作成する

1. 前提条件

    * [VS Code 用の Quantum Development Kit 拡張機能](xref:microsoft.quantum.install.cs)をインストールする

1. 新しいプロジェクトを作成します。

    * **ビュー**  ->  **コマンドパレット**にアクセス
    * [ **Q #: 新しいプロジェクトの作成**] を選択します。
    * **スタンドアロンコンソールアプリケーション**の選択
    * アプリケーションの作成先となるファイル システム上の場所に移動します。
    * プロジェクトが作成されたら、**[Open new project...]\(新しいプロジェクトを開く...\)** ボタンをクリックします。

1. アプリケーションを実行します。

    * ターミナルの**Terminal**  ->  **新しいターミナル**にアクセス
    * 「`dotnet run`」と入力します
    * 出力ウィンドウに `Hello quantum world!` というテキストが表示されます。

Visual Studio Code を使用して、quantum の開発を続けることができるようになりました。

> [!NOTE]
> * 複数のルート フォルダーを持つワークスペースは、Visual Studio Code の拡張機能では現在サポートされていません。 1 つの VS Code ワークスペース内に複数のプロジェクトがある場合は、すべてのプロジェクトが同じルート フォルダー内に含まれている必要があります。

## <a name="create-a-c-project-using-the-dotnet-command-line-tool"></a>コマンドラインツールを使用して C# プロジェクトを作成する `dotnet`

1. 前提条件

    * [コマンドライン用の Quantum 開発キット](xref:microsoft.quantum.install.standalone)をインストールする

1. 新しいアプリケーションを作成する

    ```dotnetcli
    dotnet new console -lang Q# -o <project name>
    ```

1. 新しいアプリケーション ディレクトリに移動します。

    ```
    cd <project name>
    ```

    アプリケーションのプロジェクト ファイルと共に、Q# ファイル (`Operation.qs`) と C# ホスト ファイル (`Driver.cs`) の 2 つのファイルが作成されていることがわかります。

1. アプリケーションの実行

    ```dotnetcli
    dotnet run
    ```

    `Hello quantum world!` という出力が表示されます。

これで、コマンドラインツールを使用して、クォンタム開発を続行できます。

## <a name="next-steps"></a>次の手順

お好みの環境でプロジェクトを作成したので、量子開発を続けることができます。
