---
title: Q# と Python を使用した開発
description: Python を使用して Q# アプリケーションを作成する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.python
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1ec40b6f1b7a8d9144860e3b8cfd554eb51bae81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844267"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="e49fb-103">Q# と Python を使用した開発</span><span class="sxs-lookup"><span data-stu-id="e49fb-103">Develop with Q# and Python</span></span>

<span data-ttu-id="e49fb-104">QDK をインストールして、Q# の演算を呼び出す Python のホスト プログラムを開発します。</span><span class="sxs-lookup"><span data-stu-id="e49fb-104">Install the QDK to develop Python host programs to call Q# operations.</span></span>

## <a name="install-the-qsharp-python-package"></a><span data-ttu-id="e49fb-105">`qsharp` Python パッケージをインストールする</span><span class="sxs-lookup"><span data-stu-id="e49fb-105">Install the `qsharp` Python package</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="e49fb-106">conda を使用してインストールする (推奨)</span><span class="sxs-lookup"><span data-stu-id="e49fb-106">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="e49fb-107">[Miniconda](https://docs.conda.io/en/latest/miniconda.html) または [Anaconda](https://www.anaconda.com/products/individual#Downloads) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-107">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="e49fb-108">**注:** 64 ビット のインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="e49fb-108">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="e49fb-109">Anaconda プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-109">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="e49fb-110">または、PowerShell または pwsh を使用する場合は、シェルを開いて `conda init powershell` を実行し、シェルを閉じてから再度開きます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-110">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="e49fb-111">次のコマンドを実行して、`qsharp-env` という名前の新しい conda 環境を作成し、必要なパッケージ (Jupyter Notebook と IQ# を含む) を使用してアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="e49fb-111">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="e49fb-112">同じターミナルから `python -c "import qsharp"` を実行してインストールを確認し、必要なすべての QDK コンポーネントをローカル パッケージ キャッシュに取り込みます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-112">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-and-pip-advanced"></a>[<span data-ttu-id="e49fb-113">.NET CLI と pip を使用したインストール (上級者向け)</span><span class="sxs-lookup"><span data-stu-id="e49fb-113">Install using .NET CLI and pip (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="e49fb-114">前提条件:</span><span class="sxs-lookup"><span data-stu-id="e49fb-114">Prerequisites:</span></span>

    - <span data-ttu-id="e49fb-115">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="e49fb-115">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="e49fb-116">[PIP](https://pip.pypa.io/en/stable/installing) Python パッケージ マネージャー</span><span class="sxs-lookup"><span data-stu-id="e49fb-116">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="e49fb-117">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="e49fb-117">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="e49fb-118">Q# と Python の相互運用を可能にする Python パッケージである、`qsharp` パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-118">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="e49fb-119">Jupyter と Python によって使用され、Q# の演算をコンパイルおよび実行するコア機能を提供するカーネルである、IQ# をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-119">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and running Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="e49fb-120">`dotnet iqsharp install` の手順でエラーが発生する場合、新しいターミナル ウィンドウを開いてもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="e49fb-120">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="e49fb-121">それでもうまく動作しない場合は、インストールされた `dotnet-iqsharp` ツール (Windows では `dotnet-iqsharp.exe`) の場所を確認して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="e49fb-121">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="e49fb-122">ここで、`/path/to/dotnet-iqsharp` は自分のファイル システムでの `dotnet-iqsharp` ツールの絶対パスに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="e49fb-122">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="e49fb-123">通常は、ユーザー プロファイル フォルダーの `.dotnet/tools` にあります。</span><span class="sxs-lookup"><span data-stu-id="e49fb-123">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
<span data-ttu-id="e49fb-124">\*\*_</span><span class="sxs-lookup"><span data-stu-id="e49fb-124">\*\*_</span></span>

<span data-ttu-id="e49fb-125">これで完了です。</span><span class="sxs-lookup"><span data-stu-id="e49fb-125">That's it!</span></span> <span data-ttu-id="e49fb-126">`qsharp` Python パッケージと Jupyter 用の IQ# カーネルの両方が用意されました。これらは、Python から Q# 演算をコンパイルして実行するためのコア機能を提供し、Q# 用の Jupyter Notebooks を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-126">You now have both the `qsharp` Python package and the IQ# kernel for Jupyter, which provide the core functionality for compiling and running Q# operations from Python and allows you to use Q# Jupyter Notebooks.</span></span>

## <a name="choose-your-ide"></a><span data-ttu-id="e49fb-127">IDE を選択する</span><span class="sxs-lookup"><span data-stu-id="e49fb-127">Choose your IDE</span></span>

<span data-ttu-id="e49fb-128">どんな IDE でも Q# と Python を一緒に使用することはできますが、Q# と Python のアプリケーションには Visual Studio Code (VS Code) IDE を使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-128">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="e49fb-129">QDK Visual Studio Code 拡張機能を使用すると、警告、構文の強調表示、プロジェクト テンプレートなど、豊富な機能にアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="e49fb-129">With the QDK Visual Studio Code extension you gain access to richer functionality such as warnings, syntax highlighting, project templates, and more.</span></span>

<span data-ttu-id="e49fb-130">VS Code を使用する場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-130">If you would like to use VS Code:</span></span>

- <span data-ttu-id="e49fb-131">[VS Code](https://code.visualstudio.com/download) (Windows、Linux、Mac) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-131">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac).</span></span>
- <span data-ttu-id="e49fb-132">[VS Code 用 QDK 拡張機能](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)をインストールします</span><span class="sxs-lookup"><span data-stu-id="e49fb-132">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

<span data-ttu-id="e49fb-133">別のエディターを使用する場合は、上記の手順ですべてが設定されています。</span><span class="sxs-lookup"><span data-stu-id="e49fb-133">If you would like to use a different editor, the instructions above have you all set.</span></span>

## <a name="write-your-first-q-program"></a><span data-ttu-id="e49fb-134">最初の Q# プログラムを作成する</span><span class="sxs-lookup"><span data-stu-id="e49fb-134">Write your first Q# program</span></span>

<span data-ttu-id="e49fb-135">これで、簡単な Q# プログラムを作成して実行することで、`qsharp` Python パッケージのインストールを確認する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="e49fb-135">Now you are ready to verify your `qsharp` Python package installation by writing and running a simple Q# program.</span></span>

1. <span data-ttu-id="e49fb-136">`Operation.qs` という名前のファイルを作成し、次のコードを追加して、最小限の Q# 演算を作成します。</span><span class="sxs-lookup"><span data-stu-id="e49fb-136">Create a minimal Q# operation by creating a file called `Operation.qs` and adding the following code to it:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="3-14":::

1. <span data-ttu-id="e49fb-137">`Operation.qs` と同じフォルダーに `host.py` という名前の Python プログラムを作成し、Q# の `SampleQuantumRandomNumberGenerator()` 演算をシミュレートします。</span><span class="sxs-lookup"><span data-stu-id="e49fb-137">In the same folder as `Operation.qs`, create a Python program called `host.py` to simulate the Q# `SampleQuantumRandomNumberGenerator()` operation:</span></span>

    ```python
    import qsharp
    from Qrng import SampleQuantumRandomNumberGenerator

    print(SampleQuantumRandomNumberGenerator.simulate())
    ```

1. <span data-ttu-id="e49fb-138">インストール時に作成した環境 (`qsharp` をインストールした conda または Python 環境) で、次のプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="e49fb-138">From the environment you created during installation (i.e., the conda or Python environment where you installed `qsharp`), run the program:</span></span>

    ```
    python host.py
    ```

1. <span data-ttu-id="e49fb-139">呼び出された演算の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-139">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="e49fb-140">この場合、演算によってランダムな結果が生成されるため、`0` または `1` が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-140">In this case, because your operation generates a random result, you will see either `0` or `1` printed on the screen.</span></span> <span data-ttu-id="e49fb-141">プログラムを繰り返し実行すると、それぞれの結果がだいたい半分ずつ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-141">If you run the program repeatedly, you should see each result approximately half the time.</span></span>

> [!NOTE]
> <span data-ttu-id="e49fb-142">_ その Python コードは通常の Python プログラムです。</span><span class="sxs-lookup"><span data-stu-id="e49fb-142">_ The Python code is just a normal Python program.</span></span> <span data-ttu-id="e49fb-143">Python ベースの Jupyter Notebook を含む任意の Python 環境を使用して、Python プログラムを記述し、Q# 演算を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-143">You can use any Python environment, including Python-based Jupyter Notebooks, to write the Python program and call Q# operations.</span></span> <span data-ttu-id="e49fb-144">Python プログラムでは、Python コード自体と同じフォルダーにある任意の .qs ファイルから Q# 演算をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-144">The Python program can import Q# operations from any .qs files located in the same folder as the Python code itself.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e49fb-145">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e49fb-145">Next steps</span></span>

<span data-ttu-id="e49fb-146">これで、使用している環境で Quantum Development Kit をテストできたので、こちらのチュートリアルに従って[最初の量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e49fb-146">Now that you have tested the Quantum Development Kit in your preferred environment, you can follow this tutorial to write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
