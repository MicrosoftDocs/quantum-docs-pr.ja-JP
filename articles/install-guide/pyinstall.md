---
title: 'Q # + Python を使用した開発'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76831003"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="3ee50-102">Q # + Python を使用した開発</span><span class="sxs-lookup"><span data-stu-id="3ee50-102">Develop with Q# + Python</span></span>

<span data-ttu-id="3ee50-103">QDK をインストールして、Q # 操作を呼び出す Python ホストプログラムを開発します。</span><span class="sxs-lookup"><span data-stu-id="3ee50-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="3ee50-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="3ee50-104">Pre-requisites</span></span>

    - <span data-ttu-id="3ee50-105">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="3ee50-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="3ee50-106">[PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="3ee50-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="3ee50-107">.NET Core SDK 3.1 以降</span><span class="sxs-lookup"><span data-stu-id="3ee50-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="3ee50-108">`qsharp` パッケージをインストールします。これは、Q # と Python の間の相互運用を可能にする Python パッケージです。</span><span class="sxs-lookup"><span data-stu-id="3ee50-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="3ee50-109">Q # 操作をコンパイルおよび実行するためのコア機能を提供する Jupyter および Python で使用されるカーネル `iqsharp`をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3ee50-109">Install `iqsharp`, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="3ee50-110">任意の IDE で Q # と Python を使用できますが、Q # + Python アプリケーションには Visual Studio Code (VS Code) IDE を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ee50-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="3ee50-111">Visual Studio Code と QDK Visual Studio Code 拡張機能を使用すると、豊富な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3ee50-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="3ee50-112">[VS Code](https://code.visualstudio.com/download)のインストール (Windows、Linux、および Mac)</span><span class="sxs-lookup"><span data-stu-id="3ee50-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="3ee50-113">[VS Code 用の Qdk 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3ee50-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="3ee50-114">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="3ee50-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="3ee50-115">`Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="3ee50-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="3ee50-116">Q# `SayHello()` 操作を呼び出す `hello_world.py` という名前の Python プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ee50-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="3ee50-117">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ee50-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="3ee50-118">出力を検証します。</span><span class="sxs-lookup"><span data-stu-id="3ee50-118">Verify the output.</span></span> <span data-ttu-id="3ee50-119">プログラムから次の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="3ee50-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="3ee50-120">Python Jupyter notebook を使用して、従来の Python プログラムを作成し、そのセルから Q # 操作を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="3ee50-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="3ee50-121">Python コードは、通常の Python プログラムにすぎません。</span><span class="sxs-lookup"><span data-stu-id="3ee50-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="3ee50-122">次に、</span><span class="sxs-lookup"><span data-stu-id="3ee50-122">What's next?</span></span>

<span data-ttu-id="3ee50-123">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.write-program)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3ee50-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
