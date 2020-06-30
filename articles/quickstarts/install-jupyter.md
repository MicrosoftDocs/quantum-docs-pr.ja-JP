---
title: Q# 用の Jupyter Notebook を使用した開発
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274093"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q# 用の Jupyter Notebook を使用した開発

Q# 用の Jupyter Notebook で Q# の演算を開発するための QDK をインストールします。

Jupyter Notebook には、手順書、ノート、その他のコンテンツが含まれるだけでなく、インプレース コードの実行が可能です。 この環境は、組み込まれた説明や、量子コンピューティングの対話型チュートリアルを使用しながら Q# コードを作成するのに最適です。 独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。

IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。

> [!NOTE]
> * Q# 用の Jupyter Notebook では Q# コードを実行することだけが可能で、外部のホスト プログラム (Python や C# ファイルなど) から演算を呼び出すことはできません。 外部の従来のホスト プログラムを量子プログラムと組み合わせることが目標である場合は、この環境は適切ではありません。

1. 前提条件

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. `iqsharp` パッケージのインストール

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

1. `Hello World` アプリケーションを作成してインストールを確認する

    - 次のコマンドを実行して、Notebook サーバーを起動します。

        ```
        jupyter notebook
        ```

    - Jupyter Notebook を開くには、コマンド ラインに表示された URL をコピーして、ブラウザーに貼り付けます。

    - Q# カーネルを使用して Jupyter ノートブックを作成し、最初のノートブックのセルに次のコードを追加します。

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Notebook のこのセルを実行します。

        ![Q# コードを含む Jupyter Notebook のセル](~/media/install-guide-jupyter.png)

        セルの出力に `SayHello` が表示されます。 Jupyter Notebook で実行すると、Q# コードがコンパイルされ、見つかった演算の名前がノートブックに出力されます。


    - 新しいセルで、`%simulate` コマンドを使用して、(シミュレーターで) 作成したばかりの演算を実行します。

        ![%simulate マジックを含む Jupyter Notebook のセル](~/media/install-guide-jupyter-simulate.png)

        メッセージと、呼び出した演算の結果が画面に表示されます (演算は単に `Unit` 型を返すだけなので、この場合は空のタプル `()` です)。

## <a name="next-steps"></a>次のステップ

Q# 用の Jupyter Notebook 向けの QDK をインストールできたので、Jupyter Notebook 環境内で直接 Q# コードを作成することにより、[初めての量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。

Q# 用の Jupyter Notebook で行えることの他の例については、次を参照してください。
- [Q# と Jupyter Notebook の紹介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) この環境での Q# の使用方法を示す、Q# 用の Jupyter Notebook が説明されています。
- [Quantum Katas](xref:microsoft.quantum.overview.katas)。オープンソースの自習用チュートリアルのコレクションと、Q# 用の Jupyter Notebook の形式でのプログラミング演習のセットが含まれています。 [Quantum Katas のチュートリアル ノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適したものです。 Quantum Katas は、量子コンピューティングと Q# プログラミングの要素を同時に学ぶことを目的としています。 Q# 用の Jupyter Notebook で作成できるコンテンツの優れた例が含まれています。
