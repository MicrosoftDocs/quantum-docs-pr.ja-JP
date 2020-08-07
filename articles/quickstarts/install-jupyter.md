---
title: Q# 用の Jupyter Notebook を使用した開発
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 10b1faafa70c87a99ea09916e2c386b32f9a570f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866810"
---
# <a name="develop-with-no-locq-jupyter-notebooks"></a><span data-ttu-id="ed655-102">Q# 用の Jupyter Notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="ed655-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="ed655-103">Q# 用の Jupyter Notebook で Q# の演算を開発するための QDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed655-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="ed655-104">Jupyter Notebook には、手順書、ノート、その他のコンテンツが含まれるだけでなく、インプレース コードの実行が可能です。</span><span class="sxs-lookup"><span data-stu-id="ed655-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="ed655-105">この環境は、組み込まれた説明や、量子コンピューティングの対話型チュートリアルを使用しながら Q# コードを作成するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="ed655-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="ed655-106">独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed655-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

> [!NOTE]
> * <span data-ttu-id="ed655-107">Q# 用の Jupyter Notebook では Q# コードを実行することだけが可能で、外部のホスト プログラム (Python や C# ファイルなど) から演算を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="ed655-107">In Q# Jupyter Notebooks, you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="ed655-108">外部の従来のホスト プログラムを量子プログラムと組み合わせることが目標である場合は、この環境は適切ではありません。</span><span class="sxs-lookup"><span data-stu-id="ed655-108">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

## <a name="install-the-ino-locq-jupyter-kernel"></a><span data-ttu-id="ed655-109">IQ# Jupyter カーネルをインストールする</span><span class="sxs-lookup"><span data-stu-id="ed655-109">Install the IQ# Jupyter kernel</span></span>

<span data-ttu-id="ed655-110">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ed655-110">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

### <a name="install-using-conda-recommended"></a>[<span data-ttu-id="ed655-111">conda を使用してインストールする (推奨)</span><span class="sxs-lookup"><span data-stu-id="ed655-111">Install using conda (recommended)</span></span>](#tab/tabid-conda)

1. <span data-ttu-id="ed655-112">[Miniconda](https://docs.conda.io/en/latest/miniconda.html) または [Anaconda](https://www.anaconda.com/products/individual#Downloads) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed655-112">Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) or [Anaconda](https://www.anaconda.com/products/individual#Downloads).</span></span> <span data-ttu-id="ed655-113">**注:** 64 ビット のインストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed655-113">**Note:** 64-bit installation required.</span></span>

1. <span data-ttu-id="ed655-114">Anaconda プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ed655-114">Open an Anaconda Prompt.</span></span>

   - <span data-ttu-id="ed655-115">または、PowerShell または pwsh を使用する場合は、シェルを開いて `conda init powershell` を実行し、シェルを閉じてから再度開きます。</span><span class="sxs-lookup"><span data-stu-id="ed655-115">Or, if you prefer to use PowerShell or pwsh: open a shell, run `conda init powershell`, then close and re-open the shell.</span></span>

1. <span data-ttu-id="ed655-116">次のコマンドを実行して、`qsharp-env` という名前の新しい conda 環境を作成し、必要なパッケージ (Jupyter Notebook と IQ# を含む) を使用してアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="ed655-116">Create and activate a new conda environment named `qsharp-env` with the required packages (including Jupyter Notebook and IQ#) by running the following commands:</span></span>

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. <span data-ttu-id="ed655-117">同じターミナルから `python -c "import qsharp"` を実行してインストールを確認し、必要なすべての QDK コンポーネントをローカル パッケージ キャッシュに取り込みます。</span><span class="sxs-lookup"><span data-stu-id="ed655-117">Run `python -c "import qsharp"` from the same terminal to verify your installation and populate your local package cache with all required QDK components.</span></span>

### <a name="install-using-net-cli-advanced"></a>[<span data-ttu-id="ed655-118">.NET CLI を使用したインストール (上級者向け)</span><span class="sxs-lookup"><span data-stu-id="ed655-118">Install using .NET CLI (advanced)</span></span>](#tab/tabid-dotnetcli)

1. <span data-ttu-id="ed655-119">前提条件:</span><span class="sxs-lookup"><span data-stu-id="ed655-119">Prerequisites:</span></span>

    - <span data-ttu-id="ed655-120">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="ed655-120">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="ed655-121">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="ed655-121">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="ed655-122">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="ed655-122">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="ed655-123">`Microsoft.Quantum.IQSharp` パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ed655-123">Install the `Microsoft.Quantum.IQSharp` package.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="ed655-124">`dotnet iqsharp install` の手順でエラーが発生する場合、新しいターミナル ウィンドウを開いてもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="ed655-124">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="ed655-125">それでもうまく動作しない場合は、インストールされた `dotnet-iqsharp` ツール (Windows では `dotnet-iqsharp.exe`) の場所を確認して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed655-125">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="ed655-126">ここで、`/path/to/dotnet-iqsharp` は自分のファイル システムでの `dotnet-iqsharp` ツールの絶対パスに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed655-126">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="ed655-127">通常は、ユーザー プロファイル フォルダーの `.dotnet/tools` にあります。</span><span class="sxs-lookup"><span data-stu-id="ed655-127">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
    
***

<span data-ttu-id="ed655-128">これで完了です。</span><span class="sxs-lookup"><span data-stu-id="ed655-128">That's it!</span></span> <span data-ttu-id="ed655-129">Jupyter 用の IQ# カーネルが用意されました。これは、Q# Jupyter Notebook から Q# 演算をコンパイルして実行するためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ed655-129">You now have the IQ# kernel for Jupyter, which provides the core functionality for compiling and executing Q# operations from Q# Jupyter Notebooks.</span></span>

## <a name="create-your-first-no-locq-notebook"></a><span data-ttu-id="ed655-130">最初の Q# ノートブックを作成する</span><span class="sxs-lookup"><span data-stu-id="ed655-130">Create your first Q# notebook</span></span>

<span data-ttu-id="ed655-131">これで、簡単な Q# 演算を作成して実行することで、Q# 用の Jupyter Notebook のインストールを確認する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="ed655-131">Now you are ready to verify your Q# Jupyter Notebook installation by writing and executing a simple Q# operation.</span></span>

1. <span data-ttu-id="ed655-132">インストール時に作成した環境 (つまり、作成した conda 環境または Jupyter をインストールした Python 環境) から、次のコマンドを実行して Jupyter Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="ed655-132">From the environment you created during installation (i.e., either the conda environment you created, or the Python environment where you installed Jupyter), run the following command to start the Jupyter Notebook server:</span></span>

    ```
    jupyter notebook
    ```

    - <span data-ttu-id="ed655-133">Jupyter Notebook がブラウザーで自動的に開かない場合は、コマンド ラインに表示された URL をコピーして、ブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ed655-133">If the Jupyter Notebook doesn't open automatically in your browser, copy and paste the URL provided by the command line into your browser.</span></span>

1. <span data-ttu-id="ed655-134">[新規] → [Q#] を選択して、Q# カーネルを使用して Jupyter Notebook を作成し、最初のノートブックのセルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="ed655-134">Choose "New" → "Q#" to create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. <span data-ttu-id="ed655-135">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ed655-135">Run this cell of the notebook:</span></span>

    ![Q# コードを含む Jupyter Notebook のセル](~/media/install-guide-jupyter.png)

    <span data-ttu-id="ed655-137">セルの出力に `SampleQuantumRandomNumberGenerator` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed655-137">You should see `SampleQuantumRandomNumberGenerator` in the output of the cell.</span></span> <span data-ttu-id="ed655-138">Jupyter Notebook で実行すると、Q# コードがコンパイルされ、見つかった演算の名前がセルに出力されます。</span><span class="sxs-lookup"><span data-stu-id="ed655-138">When running in Jupyter Notebook, the Q# code is compiled, and the cell outputs the name of any operations that it finds.</span></span>

1. <span data-ttu-id="ed655-139">新しいセルで、`%simulate` コマンドを使用して、(シミュレーターで) 作成したばかりの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="ed655-139">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

    ![%simulate マジックを含む Jupyter Notebook のセル](~/media/install-guide-jupyter-simulate.png)

    <span data-ttu-id="ed655-141">呼び出された演算の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed655-141">You should see the result of the operation you invoked.</span></span> <span data-ttu-id="ed655-142">この場合、演算によってランダムな結果が生成されるため、`Zero` または `One` が画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed655-142">In this case, because your operation generates a random result, you will see either `Zero` or `One` printed on the screen.</span></span> <span data-ttu-id="ed655-143">セルを繰り返し実行すると、それぞれの結果がだいたい半分ずつ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ed655-143">If you execute the cell repeatedly, you should see each result approximately half the time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed655-144">次のステップ</span><span class="sxs-lookup"><span data-stu-id="ed655-144">Next steps</span></span>

<span data-ttu-id="ed655-145">Q# 用の Jupyter Notebook 向けの QDK をインストールできたので、Jupyter Notebook 環境内で直接 Q# コードを作成することにより、[初めての量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="ed655-145">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="ed655-146">Q# 用の Jupyter Notebook で行えることの他の例については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed655-146">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>

- <span data-ttu-id="ed655-147">[Q# と Jupyter Notebook の紹介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)。</span><span class="sxs-lookup"><span data-stu-id="ed655-147">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="ed655-148">Jupyter 環境での Q# の使用方法の詳細を示す、Q# 用の Jupyter Notebook が説明されています。</span><span class="sxs-lookup"><span data-stu-id="ed655-148">There you will find a Q# Jupyter Notebook that provides more details on how to use Q# in the Jupyter environment.</span></span>
- <span data-ttu-id="ed655-149">[Quantum Katas](xref:microsoft.quantum.overview.katas)。オープンソースの自習用チュートリアルのコレクションと、Q# 用の Jupyter Notebook の形式でのプログラミング演習のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed655-149">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="ed655-150">[Quantum Katas のチュートリアル ノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適したものです。</span><span class="sxs-lookup"><span data-stu-id="ed655-150">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="ed655-151">Quantum Katas は、量子コンピューティングと Q# プログラミングの要素を同時に学ぶことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="ed655-151">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="ed655-152">Q# 用の Jupyter Notebook で作成できるコンテンツの優れた例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed655-152">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
