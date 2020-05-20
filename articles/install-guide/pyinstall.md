---
title: 'Q # と Python を使用した開発'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 35499daae0cd0ae329e39b43b0d8dd5a00183871
ms.sourcegitcommit: 328f45a0b64cb6b325fa9d3b3ddb74a6a7a97ee9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83660733"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="4e79f-102">Q # と Python を使用した開発</span><span class="sxs-lookup"><span data-stu-id="4e79f-102">Develop with Q# and Python</span></span>

<span data-ttu-id="4e79f-103">QDK をインストールして、Q # 操作を呼び出す Python ホストプログラムを開発します。</span><span class="sxs-lookup"><span data-stu-id="4e79f-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="4e79f-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="4e79f-104">Pre-requisites</span></span>

    - <span data-ttu-id="4e79f-105">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="4e79f-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="4e79f-106">[PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="4e79f-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="4e79f-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="4e79f-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="4e79f-108">パッケージをインストールします。これは、 `qsharp` Q # と python の間の相互運用を可能にする python パッケージです。</span><span class="sxs-lookup"><span data-stu-id="4e79f-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="4e79f-109">Jupyter および Python で使用されるカーネルである IQ # をインストールします。これは、Q # 操作をコンパイルおよび実行するためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e79f-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="4e79f-110">任意の IDE で Q # と Python を使用できますが、Q # + Python アプリケーションには Visual Studio Code (VS Code) IDE を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e79f-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="4e79f-111">Visual Studio Code と QDK Visual Studio Code 拡張機能を使用すると、豊富な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="4e79f-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="4e79f-112">[VS Code](https://code.visualstudio.com/download)のインストール (Windows、Linux、および Mac)</span><span class="sxs-lookup"><span data-stu-id="4e79f-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="4e79f-113">[VS Code 用の Qdk 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4e79f-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="4e79f-114">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="4e79f-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4e79f-115">`Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="4e79f-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="4e79f-116">Q# `SayHello()` 操作を呼び出す `hello_world.py` という名前の Python プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="4e79f-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="4e79f-117">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="4e79f-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="4e79f-118">出力を検証します。</span><span class="sxs-lookup"><span data-stu-id="4e79f-118">Verify the output.</span></span> <span data-ttu-id="4e79f-119">プログラムから次の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="4e79f-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="4e79f-120">Python Jupyter notebook を使用して、従来の Python プログラムを作成し、そのセルから Q # 操作を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4e79f-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="4e79f-121">Python コードは、通常の Python プログラムにすぎません。</span><span class="sxs-lookup"><span data-stu-id="4e79f-121">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e79f-122">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4e79f-122">Next steps</span></span>

<span data-ttu-id="4e79f-123">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4e79f-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
