---
title: Q# と Python を使用した開発
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 4d148435f01d975e690828dd02335758fc71dfe4
ms.sourcegitcommit: 2f4c637e194dc2b5d18539469ed37444e2800199
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "87436547"
---
# <a name="develop-with-q-and-python"></a>Q# と Python を使用した開発

QDK をインストールして、Q# の演算を呼び出す Python のホスト プログラムを開発します。

## <a name="install-the-qsharp-python-package"></a>`qsharp` Python パッケージをインストールする

### <a name="install-using-conda-recommended"></a>[conda を使用してインストールする (推奨)](#tab/tabid-conda)

1. [Miniconda](https://docs.conda.io/en/latest/miniconda.html) または [Anaconda](https://www.anaconda.com/products/individual#Downloads) をインストールします。 **注:** 64 ビット のインストールが必要です。

1. Anaconda プロンプトを開きます。

   - または、PowerShell または pwsh を使用する場合は、シェルを開いて `conda init powershell` を実行し、シェルを閉じてから再度開きます。

1. 次のコマンドを実行して、`qsharp-env` という名前の新しい conda 環境を作成し、必要なパッケージ (Jupyter Notebook と IQ# を含む) を使用してアクティブ化します。

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. 同じターミナルから `python -c "import qsharp"` を実行してインストールを確認し、必要なすべての QDK コンポーネントをローカル パッケージ キャッシュに取り込みます。

### <a name="install-using-net-cli-and-pip-advanced"></a>[.NET CLI と pip を使用したインストール (上級者向け)](#tab/tabid-dotnetcli)

1. 前提条件:

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. Q# と Python の相互運用を可能にする Python パッケージである、`qsharp` パッケージをインストールします。

    ```
    pip install qsharp
    ```

1. Jupyter と Python によって使用され、Q# の演算をコンパイルおよび実行するコア機能を提供するカーネルである、IQ# をインストールします。

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > `dotnet iqsharp install` の手順でエラーが発生する場合、新しいターミナル ウィンドウを開いてもう一度試してください。
    > それでもうまく動作しない場合は、インストールされた `dotnet-iqsharp` ツール (Windows では `dotnet-iqsharp.exe`) の場所を確認して、次を実行します。
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > ここで、`/path/to/dotnet-iqsharp` は自分のファイル システムでの `dotnet-iqsharp` ツールの絶対パスに置き換える必要があります。
    > 通常は、ユーザー プロファイル フォルダーの `.dotnet/tools` にあります。
    
***

これで完了です。 `qsharp` Python パッケージと Jupyter 用の IQ# カーネルの両方が用意されました。これらは、Python から Q# 演算をコンパイルして実行するためのコア機能を提供し、Q# 用の Jupyter Notebooks を使用できるようにします。

## <a name="choose-your-ide"></a>IDE を選択する

どんな IDE でも Q# と Python を一緒に使用することはできますが、Q# と Python のアプリケーションには Visual Studio Code (VS Code) IDE を使用することを強くお勧めします。 QDK Visual Studio Code 拡張機能を使用すると、警告、構文の強調表示、プロジェクト テンプレートなど、豊富な機能にアクセスできるようになります。

VS Code を使用する場合は、次のようにします。

- [VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をインストールします。
- [VS Code 用 QDK 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします

別のエディターを使用する場合は、上記の手順ですべてが設定されています。

## <a name="write-your-first-q-program"></a>最初の Q# プログラムを作成する

これで、簡単な Q# プログラムを作成して実行することで、`qsharp` Python パッケージのインストールを確認する準備ができました。

1. `Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 演算を作成します。

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. `Operation.qs` と同じフォルダーに `host.py` という名前の Python プログラムを作成し、Q# の `SampleQuantumRandomNumberGenerator()` 演算をシミュレートします。

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. インストール時に作成した環境 (`qsharp` をインストールした conda または Python 環境) で、次のプログラムを実行します。

    ```
    python host.py
    ```

1. 呼び出された演算の結果が表示されます。 この場合、演算によってランダムな結果が生成されるため、`0` または `1` が画面に表示されます。 プログラムを繰り返し実行すると、それぞれの結果がだいたい半分ずつ表示されます。

> [!NOTE]
> * その Python コードは通常の Python プログラムです。 Python ベースの Jupyter Notebook を含む任意の Python 環境を使用して、Python プログラムを記述し、Q# 演算を呼び出すことができます。 Python プログラムでは、Python コード自体と同じフォルダーにある任意の .qs ファイルから Q# 演算をインポートできます。

## <a name="next-steps"></a>次のステップ

これで、使用している環境に Quantum Development Kit がインストールされたので、こちらのチュートリアルに従って[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。
