---
title: Q# 用の Jupyter Notebook を使用した開発
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: bbd1f58ba7de205e452be7bac72b5fd78e7acd56
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871452"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q# 用の Jupyter Notebook を使用した開発

Q# 用の Jupyter Notebook で Q# の演算を開発するための QDK をインストールします。

Jupyter Notebook には、手順書、ノート、その他のコンテンツが含まれるだけでなく、インプレース コードの実行が可能です。 この環境は、組み込まれた説明や、量子コンピューティングの対話型チュートリアルを使用しながら Q# コードを作成するのに最適です。 独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。

> [!NOTE]
> * Q# 用の Jupyter Notebook では Q# コードを実行することだけが可能で、外部のホスト プログラム (Python や C# ファイルなど) から演算を呼び出すことはできません。 外部の従来のホスト プログラムを量子プログラムと組み合わせることが目標である場合は、この環境は適切ではありません。

## <a name="install-the-iq-jupyter-kernel"></a>IQ# Jupyter カーネルをインストールする

IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。

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

### <a name="install-using-net-cli-advanced"></a>[.NET CLI を使用したインストール (上級者向け)](#tab/tabid-dotnetcli)

1. 前提条件:

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. `Microsoft.Quantum.IQSharp` パッケージをインストールします。

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

これで完了です。 Jupyter 用の IQ# カーネルが用意されました。これは、Q# Jupyter Notebook から Q# 演算をコンパイルして実行するためのコア機能を提供します。

## <a name="create-your-first-q-notebook"></a>最初の Q# ノートブックを作成する

これで、簡単な Q# 演算を作成して実行することで、Q# 用の Jupyter Notebook のインストールを確認する準備ができました。

1. インストール時に作成した環境 (つまり、作成した conda 環境または Jupyter をインストールした Python 環境) から、次のコマンドを実行して Jupyter Notebook サーバーを起動します。

    ```
    jupyter notebook
    ```

    - Jupyter Notebook がブラウザーで自動的に開かない場合は、コマンド ラインに表示された URL をコピーして、ブラウザーに貼り付けます。

1. [新規] → [Q#] を選択して、Q# カーネルを使用して Jupyter Notebook を作成し、最初のノートブックのセルに次のコードを追加します。

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Notebook のこのセルを実行します。

    ![Q# コードを含む Jupyter Notebook のセル](~/media/install-guide-jupyter.png)

    セルの出力に `SampleQuantumRandomNumberGenerator` が表示されます。 Jupyter Notebook で実行すると、Q# コードがコンパイルされ、見つかった演算の名前がセルに出力されます。

1. 新しいセルで、`%simulate` コマンドを使用して、(シミュレーターで) 作成したばかりの演算を実行します。

    ![%simulate マジックを含む Jupyter Notebook のセル](~/media/install-guide-jupyter-simulate.png)

    呼び出された演算の結果が表示されます。 この場合、演算によってランダムな結果が生成されるため、`Zero` または `One` が画面に表示されます。 セルを繰り返し実行すると、それぞれの結果がだいたい半分ずつ表示されます。

## <a name="next-steps"></a>次のステップ

Q# 用の Jupyter Notebook 向けの QDK をインストールできたので、Jupyter Notebook 環境内で直接 Q# コードを作成することにより、[初めての量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。

Q# 用の Jupyter Notebook で行えることの他の例については、次を参照してください。

- [Q# と Jupyter Notebook の紹介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) Jupyter 環境での Q# の使用方法の詳細を示す、Q# 用の Jupyter Notebook が説明されています。
- [Quantum Katas](xref:microsoft.quantum.overview.katas)。オープンソースの自習用チュートリアルのコレクションと、Q# 用の Jupyter Notebook の形式でのプログラミング演習のセットが含まれています。 [Quantum Katas のチュートリアル ノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適したものです。 Quantum Katas は、量子コンピューティングと Q# プログラミングの要素を同時に学ぶことを目的としています。 Q# 用の Jupyter Notebook で作成できるコンテンツの優れた例が含まれています。
