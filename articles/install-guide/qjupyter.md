---
title: Q# 用の Jupyter Notebook を使用した開発
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: b80d95a160b5f46c1132d3428ba32ad6dcd5656e
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630330"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="cbc85-102">Q# 用の Jupyter Notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="cbc85-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="cbc85-103">Q # Jupyter Notebook で Q # 操作を開発するには、QDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="cbc85-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="cbc85-104">Jupyter Notebook を使用すると、命令、メモ、およびその他のコンテンツと共に、インプレースコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cbc85-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="cbc85-105">この環境は、記述された説明や量子コンピューティングの対話型チュートリアルを使用して Q # コードを記述する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="cbc85-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="cbc85-106">独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbc85-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="cbc85-107">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="cbc85-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="cbc85-108">Q # Jupyter Notebook では、Q # コードのみを実行できます。また、操作を外部ホストプログラム (Python や C# ファイルなど) から呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="cbc85-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="cbc85-109">この環境は、外部のクラシックホストプログラムを quantum プログラムと組み合わせることが目的の場合には適していません。</span><span class="sxs-lookup"><span data-stu-id="cbc85-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="cbc85-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="cbc85-110">Prerequisites</span></span>

    - <span data-ttu-id="cbc85-111">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="cbc85-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="cbc85-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="cbc85-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="cbc85-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="cbc85-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="cbc85-114">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="cbc85-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="cbc85-115">手順の実行中にエラーが発生した場合は `dotnet iqsharp install` 、新しいターミナルウィンドウを開いて、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="cbc85-115">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="cbc85-116">それでも問題が解決しない場合は、インストールされている `dotnet-iqsharp` ツール (Windows の場合) を見つけて、次を実行してみてください `dotnet-iqsharp.exe` 。</span><span class="sxs-lookup"><span data-stu-id="cbc85-116">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="cbc85-117">は、 `/path/to/dotnet-iqsharp` `dotnet-iqsharp` ファイルシステム内のツールへの絶対パスに置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbc85-117">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="cbc85-118">通常、これは `.dotnet/tools` ユーザープロファイルフォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="cbc85-118">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>

1. <span data-ttu-id="cbc85-119">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="cbc85-119">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="cbc85-120">次のコマンドを実行して、Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="cbc85-120">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="cbc85-121">Jupyter Notebook を開くには、コマンドラインで指定した URL をコピーしてブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="cbc85-121">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="cbc85-122">Q # カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="cbc85-122">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="cbc85-123">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbc85-123">Run this cell of the notebook:</span></span>

        ![Q # コードを含むセルを Jupyter Notebook](~/media/install-guide-jupyter.png)

        <span data-ttu-id="cbc85-125">セルの出力に `SayHello` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbc85-125">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="cbc85-126">Jupyter Notebook で実行すると、Q # コードがコンパイルされ、ノートブックによって検出された操作の名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="cbc85-126">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="cbc85-127">新しいセルで、次のコマンドを使用して、先ほど作成した操作 (シミュレーター) を実行し `%simulate` ます。</span><span class="sxs-lookup"><span data-stu-id="cbc85-127">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![% シミュレートマジックを含むセルを Jupyter Notebook](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="cbc85-129">画面には、呼び出された操作の結果と共に、メッセージが出力されます (ここでは、操作が単純に型を返すため、空のタプルが表示されて `()` `Unit` います)。</span><span class="sxs-lookup"><span data-stu-id="cbc85-129">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cbc85-130">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cbc85-130">Next steps</span></span>

<span data-ttu-id="cbc85-131">Q # Jupyter Notebook 用の QDK をインストールしたので、Jupyter Notebook 環境内で直接 Q # コードを記述して、[最初のクォンタムプログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="cbc85-131">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="cbc85-132">Q # Jupyter Notebook でできることの詳細な例については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbc85-132">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="cbc85-133">[Q # と Jupyter Notebook の概要を](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)紹介します。</span><span class="sxs-lookup"><span data-stu-id="cbc85-133">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="cbc85-134">ここでは、この環境で Q # を使用する方法を示す Q # Jupyter Notebook について説明します。</span><span class="sxs-lookup"><span data-stu-id="cbc85-134">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="cbc85-135">[Quantum Katas](xref:microsoft.quantum.overview.katas)は、自習形式のチュートリアルのオープンソースのコレクションであり、Q # Jupyter notebook の形式でプログラミング演習を行います。</span><span class="sxs-lookup"><span data-stu-id="cbc85-135">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="cbc85-136">[Quantum Katas のチュートリアルノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適しています。</span><span class="sxs-lookup"><span data-stu-id="cbc85-136">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="cbc85-137">Quantum Katas は、クォンタムコンピューティングと Q # プログラミングの要素を同時に教育することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="cbc85-137">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="cbc85-138">これは、Q # Jupyter Notebook を使用して作成できるコンテンツの種類の優れた例です。</span><span class="sxs-lookup"><span data-stu-id="cbc85-138">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
