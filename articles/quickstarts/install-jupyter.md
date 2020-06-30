---
title: Q# 用の Jupyter Notebook を使用した開発
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 5c613d29c03525d29893307684f13ccd32d4d4eb
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274093"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="c1eca-102">Q# 用の Jupyter Notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="c1eca-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="c1eca-103">Q# 用の Jupyter Notebook で Q# の演算を開発するための QDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c1eca-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="c1eca-104">Jupyter Notebook には、手順書、ノート、その他のコンテンツが含まれるだけでなく、インプレース コードの実行が可能です。</span><span class="sxs-lookup"><span data-stu-id="c1eca-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="c1eca-105">この環境は、組み込まれた説明や、量子コンピューティングの対話型チュートリアルを使用しながら Q# コードを作成するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="c1eca-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="c1eca-106">独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1eca-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="c1eca-107">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="c1eca-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="c1eca-108">Q# 用の Jupyter Notebook では Q# コードを実行することだけが可能で、外部のホスト プログラム (Python や C# ファイルなど) から演算を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="c1eca-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="c1eca-109">外部の従来のホスト プログラムを量子プログラムと組み合わせることが目標である場合は、この環境は適切ではありません。</span><span class="sxs-lookup"><span data-stu-id="c1eca-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="c1eca-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="c1eca-110">Prerequisites</span></span>

    - <span data-ttu-id="c1eca-111">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="c1eca-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="c1eca-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="c1eca-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="c1eca-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="c1eca-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="c1eca-114">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="c1eca-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="c1eca-115">`dotnet iqsharp install` の手順でエラーが発生する場合、新しいターミナル ウィンドウを開いてもう一度試してください。</span><span class="sxs-lookup"><span data-stu-id="c1eca-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="c1eca-116">それでもうまく動作しない場合は、インストールされた `dotnet-iqsharp` ツール (Windows では `dotnet-iqsharp.exe`) の場所を確認して、次を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1eca-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="c1eca-117">ここで、`/path/to/dotnet-iqsharp` は自分のファイル システムでの `dotnet-iqsharp` ツールの絶対パスに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1eca-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="c1eca-118">通常は、ユーザー プロファイル フォルダーの `.dotnet/tools` にあります。</span><span class="sxs-lookup"><span data-stu-id="c1eca-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="c1eca-119">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="c1eca-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="c1eca-120">次のコマンドを実行して、Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="c1eca-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="c1eca-121">Jupyter Notebook を開くには、コマンド ラインに表示された URL をコピーして、ブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c1eca-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="c1eca-122">Q# カーネルを使用して Jupyter ノートブックを作成し、最初のノートブックのセルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="c1eca-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="c1eca-123">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="c1eca-123">Run this cell of the notebook:</span></span>

        ![Q# コードを含む Jupyter Notebook のセル](~/media/install-guide-jupyter.png)

        <span data-ttu-id="c1eca-125">セルの出力に `SayHello` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1eca-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="c1eca-126">Jupyter Notebook で実行すると、Q# コードがコンパイルされ、見つかった演算の名前がノートブックに出力されます。</span><span class="sxs-lookup"><span data-stu-id="c1eca-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="c1eca-127">新しいセルで、`%simulate` コマンドを使用して、(シミュレーターで) 作成したばかりの演算を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1eca-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![%simulate マジックを含む Jupyter Notebook のセル](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="c1eca-129">メッセージと、呼び出した演算の結果が画面に表示されます (演算は単に `Unit` 型を返すだけなので、この場合は空のタプル `()` です)。</span><span class="sxs-lookup"><span data-stu-id="c1eca-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1eca-130">次のステップ</span><span class="sxs-lookup"><span data-stu-id="c1eca-130">Next steps</span></span>

<span data-ttu-id="c1eca-131">Q# 用の Jupyter Notebook 向けの QDK をインストールできたので、Jupyter Notebook 環境内で直接 Q# コードを作成することにより、[初めての量子プログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="c1eca-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="c1eca-132">Q# 用の Jupyter Notebook で行えることの他の例については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1eca-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="c1eca-133">[Q# と Jupyter Notebook の紹介](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)</span><span class="sxs-lookup"><span data-stu-id="c1eca-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="c1eca-134">この環境での Q# の使用方法を示す、Q# 用の Jupyter Notebook が説明されています。</span><span class="sxs-lookup"><span data-stu-id="c1eca-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="c1eca-135">[Quantum Katas](xref:microsoft.quantum.overview.katas)。オープンソースの自習用チュートリアルのコレクションと、Q# 用の Jupyter Notebook の形式でのプログラミング演習のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1eca-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="c1eca-136">[Quantum Katas のチュートリアル ノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適したものです。</span><span class="sxs-lookup"><span data-stu-id="c1eca-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="c1eca-137">Quantum Katas は、量子コンピューティングと Q# プログラミングの要素を同時に学ぶことを目的としています。</span><span class="sxs-lookup"><span data-stu-id="c1eca-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="c1eca-138">Q# 用の Jupyter Notebook で作成できるコンテンツの優れた例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c1eca-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
