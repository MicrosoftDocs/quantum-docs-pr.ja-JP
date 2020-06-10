---
title: 'Q # と Python を使用した開発'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630281"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="20c45-102">Q # と Python を使用した開発</span><span class="sxs-lookup"><span data-stu-id="20c45-102">Develop with Q# and Python</span></span>

<span data-ttu-id="20c45-103">QDK をインストールして、Q # 操作を呼び出す Python ホストプログラムを開発します。</span><span class="sxs-lookup"><span data-stu-id="20c45-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="20c45-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="20c45-104">Prerequisites</span></span>

    - <span data-ttu-id="20c45-105">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="20c45-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="20c45-106">[PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="20c45-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="20c45-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="20c45-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="20c45-108">パッケージをインストールします。これは、 `qsharp` Q # と python の間の相互運用を可能にする python パッケージです。</span><span class="sxs-lookup"><span data-stu-id="20c45-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="20c45-109">Jupyter および Python で使用されるカーネルである IQ # をインストールします。これは、Q # 操作をコンパイルおよび実行するためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="20c45-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="20c45-110">手順の実行中にエラーが発生した場合は `dotnet iqsharp install` 、新しいターミナルウィンドウを開いて、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="20c45-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="20c45-111">それでも問題が解決しない場合は、インストールされている `dotnet-iqsharp` ツール (Windows の場合) を見つけて、次を実行してみてください `dotnet-iqsharp.exe` 。</span><span class="sxs-lookup"><span data-stu-id="20c45-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="20c45-112">は、 `/path/to/dotnet-iqsharp` `dotnet-iqsharp` ファイルシステム内のツールへの絶対パスに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="20c45-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="20c45-113">通常、これは `.dotnet/tools` ユーザープロファイルフォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="20c45-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="20c45-114">任意の IDE で Q # と Python を使用できますが、Q # + Python アプリケーションには Visual Studio Code (VS Code) IDE を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="20c45-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="20c45-115">Visual Studio Code と QDK Visual Studio Code 拡張機能を使用すると、豊富な機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="20c45-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="20c45-116">[VS Code](https://code.visualstudio.com/download)のインストール (Windows、Linux、および Mac)</span><span class="sxs-lookup"><span data-stu-id="20c45-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="20c45-117">[VS Code 用の Qdk 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="20c45-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="20c45-118">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="20c45-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="20c45-119">`Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="20c45-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="20c45-120">Q# `SayHello()` 操作を呼び出す `hello_world.py` という名前の Python プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="20c45-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="20c45-121">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="20c45-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="20c45-122">出力を検証します。</span><span class="sxs-lookup"><span data-stu-id="20c45-122">Verify the output.</span></span> <span data-ttu-id="20c45-123">プログラムから次の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="20c45-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="20c45-124">Python Jupyter notebook を使用して、従来の Python プログラムを作成し、そのセルから Q # 操作を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="20c45-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="20c45-125">Python コードは、通常の Python プログラムにすぎません。</span><span class="sxs-lookup"><span data-stu-id="20c45-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20c45-126">次のステップ</span><span class="sxs-lookup"><span data-stu-id="20c45-126">Next steps</span></span>

<span data-ttu-id="20c45-127">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="20c45-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
