---
title: Q# 用の Jupyter Notebook を使用した開発
description: Jupyter Notebook を使用して Q# アプリケーションを作成する方法について説明します。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 51de510907ea087d1f23d3ff65d268d6d455a493
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834314"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="a200d-103">Q# 用の Jupyter Notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="a200d-103">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="a200d-104">Q# 用の Jupyter Notebook で Q# の演算を開発するための QDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a200d-104">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="a200d-105">Jupyter Notebook には、手順書、ノート、その他のコンテンツが含まれるだけでなく、インプレース コードの計算が可能です。</span><span class="sxs-lookup"><span data-stu-id="a200d-105">Jupyter Notebooks allow in-place code computation alongside instructions, notes, and other content.</span></span> <span data-ttu-id="a200d-106">この環境は、組み込まれた説明や、量子コンピューティングの対話型チュートリアルを使用しながら Q# コードを作成するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="a200d-106">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="a200d-107">独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a200d-107">Here's what you need to do to start creating your own Q# notebooks.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="a200d-108">IQ# Jupyter カーネルをインストールする</span><span class="sxs-lookup"><span data-stu-id="a200d-108">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="a200d-109">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a200d-109">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="a200d-110">conda を使用してインストールする (推奨)</span><span class="sxs-lookup"><span data-stu-id="a200d-110">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="a200d-111">[Miniconda](https://docs.conda.io/en/latest/miniconda.html) または [Anaconda](https://www.anaconda.com/products/individual#Downloads) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a200d-111">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="a200d-112">**注:** 64 ビット のインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="a200d-112">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="a200d-113">Anaconda プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="a200d-113">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="a200d-114">または、PowerShell または pwsh を使用する場合は、シェルを開いて `conda init powershell` を実行し、シェルを閉じてから再度開きます。</span><span class="sxs-lookup"><span data-stu-id="a200d-114">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="a200d-115">次のコマンドを実行して、`qsharp-env` という名前の新しい conda 環境を作成し、必要なパッケージ (Jupyter Notebook と IQ# を含む) を使用してアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="a200d-115">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="a200d-116">同じターミナルから `python -c "import qsharp"` を実行してインストールを確認し、必要なすべての QDK コンポーネントをローカル パッケージ キャッシュに取り込みます。</span><span class="sxs-lookup"><span data-stu-id="a200d-116">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="a200d-117">.NET CLI を使用したインストール (上級者向け)</span><span class="sxs-lookup"><span data-stu-id="a200d-117">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="a200d-118">前提条件:</span><span class="sxs-lookup"><span data-stu-id="a200d-118">Prerequisites:</span></span>

    - <span data-ttu-id="a200d-119">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="a200d-119">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="a200d-120">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="a200d-120">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="a200d-121">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="a200d-121">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="a200d-122">`Microsoft.Quantum.IQSharp` パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="a200d-122">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> <span data-ttu-id="a200d-123">`dotnet iqsharp install` の手順でエラーが発生する場合、新しいターミナル ウィンドウを開いてもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="a200d-123">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
> <span data-ttu-id="a200d-124">それでもうまく動作しない場合は、インストールされた `dotnet-iqsharp` ツール (Windows では `dotnet-iqsharp.exe`) の場所を確認して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="a200d-124">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> <span data-ttu-id="a200d-125">ここで、`/path/to/dotnet-iqsharp` は自分のファイル システムでの `dotnet-iqsharp` ツールの絶対パスに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="a200d-125">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
> <span data-ttu-id="a200d-126">通常は、ユーザー プロファイル フォルダーの `.dotnet/tools` にあります。</span><span class="sxs-lookup"><span data-stu-id="a200d-126">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="a200d-127">これで完了です。</span><span class="sxs-lookup"><span data-stu-id="a200d-127">That's it!</span></span> <span data-ttu-id="a200d-128">Jupyter 用の IQ# カーネルが用意されました。これは、Q# Jupyter Notebook から Q# 演算をコンパイルして実行するためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="a200d-128">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and running Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="a200d-129">最初の Q# ノートブックを作成する</span><span class="sxs-lookup"><span data-stu-id="a200d-129">Create your first Q# notebook</span></span>

<span data-ttu-id="a200d-130">これで、簡単な Q# 演算を作成して実行することで、Q# 用の Jupyter Notebook のインストールを確認する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="a200d-130">Now you are ready to verify your Q# Jupyter Notebook installation by writing and running a simple Q# operation.</span></span>

1. <span data-ttu-id="a200d-131">インストール時に作成した環境 (つまり、作成した conda 環境または Jupyter をインストールした Python 環境) から、次のコマンドを実行して Jupyter Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="a200d-131">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="a200d-132">Jupyter Notebook がブラウザーで自動的に開かない場合は、コマンド ラインに表示された URL をコピーして、ブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="a200d-132">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="a200d-133">**[新規] → [Q#]** を選択して、Q# カーネルを使用して Jupyter Notebook を作成し、最初のノートブックのセルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a200d-133">Choose **New → Q#** to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="a200d-134">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="a200d-134">Run this cell of the notebook:</span></span>

    ![Q# コードを含む Jupyter Notebook のセル](~/media/install-guide-jupyter.png)

    <span data-ttu-id="a200d-136">セルの出力に `SampleQuantumRandomNumberGenerator` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a200d-136">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="a200d-137">Jupyter Notebook で実行すると、Q# コードがコンパイルされ、見つかった演算の名前がセルに出力されます。</span><span class="sxs-lookup"><span data-stu-id="a200d-137">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="a200d-138">新しいセルで、`%simulate` コマンドを使用して、(シミュレーターで) 作成したばかりの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="a200d-138">In a new cell, run the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![%simulate マジックを含む Jupyter Notebook のセル](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="a200d-140">呼び出された演算の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a200d-140">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="a200d-141">この場合、演算によってランダムな結果が生成されるため、`Zero` または `One` が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a200d-141">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="a200d-142">セルを繰り返し実行すると、それぞれの結果がだいたい半分ずつ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a200d-142">If you run the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a200d-143">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a200d-143">Next steps</span></span>

<span data-ttu-id="a200d-144">Q# 用の Jupyter Notebook 向けの QDK をインストールできたので、Jupyter Notebook 環境内で直接 Q# コードを作成することにより、[初めての量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="a200d-144">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="a200d-145">Q# 用の Jupyter Notebook で行えることの他の例については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a200d-145">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="a200d-146">[Q# と Jupyter Notebook の紹介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="a200d-146">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="a200d-147">Jupyter 環境での Q# の使用方法の詳細を示す、Q# 用の Jupyter Notebook が説明されています。</span><span class="sxs-lookup"><span data-stu-id="a200d-147">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="a200d-148">[Quantum Katas](xref:microsoft.quantum.overview.katas)。オープンソースの自習用チュートリアルのコレクションと、Q# 用の Jupyter Notebook の形式でのプログラミング演習のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a200d-148">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="a200d-149">[Quantum Katas のチュートリアル ノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適したものです。</span><span class="sxs-lookup"><span data-stu-id="a200d-149">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="a200d-150">Quantum Katas は、量子コンピューティングと Q# プログラミングの要素を同時に学ぶことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="a200d-150">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="a200d-151">Q# 用の Jupyter Notebook で作成できるコンテンツの優れた例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a200d-151">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
