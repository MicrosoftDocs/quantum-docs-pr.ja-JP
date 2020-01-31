---
title: 'Q # Jupyter notebook を使用した開発'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b7276f9b273f601f30e4938018398353b6a9102d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831071"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Q # Jupyter notebook を使用した開発

Q # Jupyter Notebook で Q # 操作を開発するには、QDK をインストールします。

Jupyter Notebook を使用すると、命令、メモ、およびその他のコンテンツと共に、インプレースコードを実行できます。 この環境は、記述された説明や量子コンピューティングの対話型チュートリアルを使用して Q # コードを記述する場合に最適です。 独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。

IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。

> [!NOTE]
> * Q # Jupyter Notebook では、Q # コードのみを実行できます。また、操作を外部ホストプログラム (Python やC#ファイルなど) から呼び出すことはできません。 この環境は、外部のクラシックホストプログラムを quantum プログラムと組み合わせることが目的の場合には適していません。

1. 前提条件

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)

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

    - Jupyter notebook を開き、コマンドラインから提供された URL をブラウザーに貼り付けます。

    - Q# カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - Notebook のこのセルを実行します。

        ![Q# コードを含む Jupyter Notebook セル](~/media/install-guide-jupyter.png)

        セルの出力に `SayHello` が表示されます。 Jupyter Notebook で実行すると、Q# コードがコンパイルされ、ノートブックから検出した操作の名前が出力されます。


    - 新しいセルで、`%simulate` コマンドを使用して、先ほど作成した操作 (シミュレーター) を実行します。

        ![%simulate マジックのある Jupyter Notebook セル](~/media/install-guide-jupyter-simulate.png)

        画面には、呼び出された操作の結果と共に、メッセージが出力されます (ここでは、操作は単に `Unit` 型を返すため、空のタプル `()` が表示されます)。

## <a name="whats-next"></a>次に、

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。
