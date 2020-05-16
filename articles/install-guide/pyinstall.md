---
title: 'Q # と Python を使用した開発'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: a8c5b9c25c069f98ef8eefd6cfbc36bf3376931c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426359"
---
# <a name="develop-with-q-and-python"></a>Q # と Python を使用した開発

QDK をインストールして、Q # 操作を呼び出す Python ホストプログラムを開発します。

1. 前提条件

    - [Python](https://www.python.org/downloads/) 3.6 以降
    - [PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー
    - [.NET Core SDK 3.1 以降](https://www.microsoft.com/net/download)


1. パッケージをインストールします。これは、 `qsharp` Q # と python の間の相互運用を可能にする python パッケージです。

    ```bash
    pip install qsharp
    ```

1. Jupyter および Python で使用されるカーネルである IQ # をインストールします。これは、Q # 操作をコンパイルおよび実行するためのコア機能を提供します。

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. 任意の IDE で Q # と Python を使用できますが、Q # + Python アプリケーションには Visual Studio Code (VS Code) IDE を使用することを強くお勧めします。 Visual Studio Code と QDK Visual Studio Code 拡張機能を使用すると、豊富な機能にアクセスできます。

    - [VS Code](https://code.visualstudio.com/download)のインストール (Windows、Linux、および Mac)
    - [VS Code 用の Qdk 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします。

1. `Hello World` アプリケーションを作成してインストールを確認する

    - `Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
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
       ```


> [!NOTE]
> * Python Jupyter notebook を使用して、従来の Python プログラムを作成し、そのセルから Q # 操作を呼び出すこともできます。 Python コードは、通常の Python プログラムにすぎません。

## <a name="next-steps"></a>次の手順

これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。
