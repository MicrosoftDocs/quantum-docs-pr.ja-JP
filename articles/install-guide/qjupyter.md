---
title: Q# 用の Jupyter Notebook を使用した開発
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 0c4dc856c94b0a694fb99607eda64cec4d5c221d
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660760"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q# 用の Jupyter Notebook を使用した開発

Q # Jupyter Notebook で Q # 操作を開発するには、QDK をインストールします。

Jupyter Notebook を使用すると、命令、メモ、およびその他のコンテンツと共に、インプレースコードを実行できます。 この環境は、記述された説明や量子コンピューティングの対話型チュートリアルを使用して Q # コードを記述する場合に最適です。 独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。

IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。

> [!NOTE]
> * Q # Jupyter Notebook では、Q # コードのみを実行できます。また、操作を外部ホストプログラム (Python や C# ファイルなど) から呼び出すことはできません。 この環境は、外部のクラシックホストプログラムを quantum プログラムと組み合わせることが目的の場合には適していません。

1. 前提条件

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

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

    - Jupyter Notebook を開くには、コマンドラインで指定した URL をコピーしてブラウザーに貼り付けます。

    - Q # カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Notebook のこのセルを実行します。

        ![Q # コードを含むセルを Jupyter Notebook](~/media/install-guide-jupyter.png)

        セルの出力に `SayHello` が表示されます。 Jupyter Notebook で実行すると、Q # コードがコンパイルされ、ノートブックによって検出された操作の名前が出力されます。


    - 新しいセルで、次のコマンドを使用して、先ほど作成した操作 (シミュレーター) を実行し `%simulate` ます。

        ![% シミュレートマジックを含むセルを Jupyter Notebook](~/media/install-guide-jupyter-simulate.png)

        画面には、呼び出された操作の結果と共に、メッセージが出力されます (ここでは、操作が単純に型を返すため、空のタプルが表示されて `()` `Unit` います)。

## <a name="next-steps"></a>次のステップ

Q # Jupyter Notebook 用の QDK をインストールしたので、Jupyter Notebook 環境内で直接 Q # コードを記述して、[最初のクォンタムプログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。

Q # Jupyter Notebook でできることの詳細な例については、次を参照してください。
- [Q # と Jupyter Notebook の概要を](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)紹介します。 ここでは、この環境で Q # を使用する方法を示す Q # Jupyter Notebook について説明します。
- [Quantum Katas](xref:microsoft.quantum.overview.katas)は、自習形式のチュートリアルのオープンソースのコレクションであり、Q # Jupyter notebook の形式でプログラミング演習を行います。 [Quantum Katas のチュートリアルノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適しています。 Quantum Katas は、クォンタムコンピューティングと Q # プログラミングの要素を同時に教育することを目的としています。 これは、Q # Jupyter Notebook を使用して作成できるコンテンツの種類の優れた例です。
