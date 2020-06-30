---
title: Q# と Python を使用した開発
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274082"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="4ba20-102">Q# と Python を使用した開発</span><span class="sxs-lookup"><span data-stu-id="4ba20-102">Develop with Q# and Python</span></span>

<span data-ttu-id="4ba20-103">QDK をインストールして、Q# の演算を呼び出す Python のホスト プログラムを開発します。</span><span class="sxs-lookup"><span data-stu-id="4ba20-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="4ba20-104">前提条件</span><span class="sxs-lookup"><span data-stu-id="4ba20-104">Prerequisites</span></span>

    - <span data-ttu-id="4ba20-105">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="4ba20-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="4ba20-106">[PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="4ba20-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="4ba20-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="4ba20-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="4ba20-108">Q# と Python の相互運用を可能にする Python パッケージである、`qsharp` パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4ba20-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="4ba20-109">Jupyter と Python によって使用され、Q# の演算をコンパイルおよび実行するコア機能を提供するカーネルである、IQ# をインストールします。</span><span class="sxs-lookup"><span data-stu-id="4ba20-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="4ba20-110">`dotnet iqsharp install` の手順でエラーが発生する場合、新しいターミナル ウィンドウを開いてもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="4ba20-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="4ba20-111">それでもうまく動作しない場合は、インストールされた `dotnet-iqsharp` ツール (Windows では `dotnet-iqsharp.exe`) の場所を確認して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="4ba20-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="4ba20-112">ここで、`/path/to/dotnet-iqsharp` は自分のファイル システムでの `dotnet-iqsharp` ツールの絶対パスに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="4ba20-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="4ba20-113">通常は、ユーザー プロファイル フォルダーの `.dotnet/tools` にあります。</span><span class="sxs-lookup"><span data-stu-id="4ba20-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="4ba20-114">どんな IDE でも Q# と Python を一緒に使用することはできますが、Q# と Python のアプリケーションには Visual Studio Code (VS Code) IDE を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4ba20-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="4ba20-115">Visual Studio Code と QDK Visual Studio Code 拡張機能を使用することにより、さらに豊富な機能を利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4ba20-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="4ba20-116">[VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をインストールします</span><span class="sxs-lookup"><span data-stu-id="4ba20-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="4ba20-117">[VS Code 用 QDK 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします</span><span class="sxs-lookup"><span data-stu-id="4ba20-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="4ba20-118">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="4ba20-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="4ba20-119">`Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 操作を作成します。</span><span class="sxs-lookup"><span data-stu-id="4ba20-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="4ba20-120">Q# `SayHello()` 操作を呼び出す `hello_world.py` という名前の Python プログラムを作成します。</span><span class="sxs-lookup"><span data-stu-id="4ba20-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="4ba20-121">以下のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="4ba20-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="4ba20-122">出力を検証します。</span><span class="sxs-lookup"><span data-stu-id="4ba20-122">Verify the output.</span></span> <span data-ttu-id="4ba20-123">プログラムから次の行が出力されます。</span><span class="sxs-lookup"><span data-stu-id="4ba20-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="4ba20-124">また、Python の Jupyter Notebook を使用して従来の Python プログラムを作成し、セルから Q# の演算を呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="4ba20-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="4ba20-125">その Python コードは通常の Python プログラムです。</span><span class="sxs-lookup"><span data-stu-id="4ba20-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4ba20-126">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4ba20-126">Next steps</span></span>

<span data-ttu-id="4ba20-127">これで、使用している環境に Quantum Development Kit がインストールされたので、[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4ba20-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
