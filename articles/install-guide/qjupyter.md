---
title: Q# 用の Jupyter Notebook を使用した開発
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.jupyter
ms.openlocfilehash: 9117794d6cf6f05fa34e05c21fad8977d0e76505
ms.sourcegitcommit: c8ebc5d7d8581444754f5d7bfaca2f25601f1b14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84577822"
---
# <a name="develop-with-q-jupyter-notebooks"></a><span data-ttu-id="f6487-102">Q# 用の Jupyter Notebook を使用した開発</span><span class="sxs-lookup"><span data-stu-id="f6487-102">Develop with Q# Jupyter Notebooks</span></span>

<span data-ttu-id="f6487-103">Q # Jupyter Notebook で Q # 操作を開発するには、QDK をインストールします。</span><span class="sxs-lookup"><span data-stu-id="f6487-103">Install the QDK for developing Q# operations on Q# Jupyter Notebooks.</span></span>

<span data-ttu-id="f6487-104">Jupyter Notebook を使用すると、命令、メモ、およびその他のコンテンツと共に、インプレースコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6487-104">Jupyter Notebooks allow in-place code execution alongside instructions, notes, and other content.</span></span> <span data-ttu-id="f6487-105">この環境は、記述された説明や量子コンピューティングの対話型チュートリアルを使用して Q # コードを記述する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="f6487-105">This environment is ideal for writing Q# code with embedded explanations or quantum computing interactive tutorials.</span></span> <span data-ttu-id="f6487-106">独自の Q# ノートブックの作成を開始するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6487-106">Here's what you need to do to start creating your own Q# notebooks.</span></span>

<span data-ttu-id="f6487-107">IQ# (発音: アイ キュー シャープ) は主に Jupyter と Python で .NET Core SDK に対して使用される拡張機能であり、Q# の演算をコンパイルおよびシミュレートするためのコア機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f6487-107">IQ# (pronounced i-q-sharp) is an extension primarily used by Jupyter and Python to the .NET Core SDK that provides the core functionality for compiling and simulating Q# operations.</span></span>

> [!NOTE]
> * <span data-ttu-id="f6487-108">Q # Jupyter Notebook では、Q # コードのみを実行できます。また、操作を外部ホストプログラム (Python や C# ファイルなど) から呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f6487-108">In Q# Jupyter Notebooks you can only run Q# code, and the operations cannot be called from external host programs (e.g. Python or C# files).</span></span> <span data-ttu-id="f6487-109">この環境は、外部のクラシックホストプログラムを quantum プログラムと組み合わせることが目的の場合には適していません。</span><span class="sxs-lookup"><span data-stu-id="f6487-109">This environment is not appropriate if your goal is to combine an external classical host program with the quantum program.</span></span>

1. <span data-ttu-id="f6487-110">前提条件</span><span class="sxs-lookup"><span data-stu-id="f6487-110">Pre-requisites</span></span>

    - <span data-ttu-id="f6487-111">[Python](https://www.python.org/downloads/) 3.6 以降</span><span class="sxs-lookup"><span data-stu-id="f6487-111">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - [<span data-ttu-id="f6487-112">Jupyter Notebook</span><span class="sxs-lookup"><span data-stu-id="f6487-112">Jupyter Notebook</span></span>](https://jupyter.readthedocs.io/en/latest/install.html)
    - [<span data-ttu-id="f6487-113">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="f6487-113">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. <span data-ttu-id="f6487-114">`iqsharp` パッケージのインストール</span><span class="sxs-lookup"><span data-stu-id="f6487-114">Install the `iqsharp` package</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

1. <span data-ttu-id="f6487-115">`Hello World` アプリケーションを作成してインストールを確認する</span><span class="sxs-lookup"><span data-stu-id="f6487-115">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f6487-116">次のコマンドを実行して、Notebook サーバーを起動します。</span><span class="sxs-lookup"><span data-stu-id="f6487-116">Run the following command to start the notebook server:</span></span>

        ```
        jupyter notebook
        ```

    - <span data-ttu-id="f6487-117">Jupyter Notebook を開くには、コマンドラインで指定した URL をコピーしてブラウザーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f6487-117">To open the Jupyter Notebook, copy and paste the URL provided by the command line into your browser.</span></span>

    - <span data-ttu-id="f6487-118">Q # カーネルを使用して Jupyter Notebook を作成し、最初の Notebook セルに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f6487-118">Create a Jupyter Notebook with a Q# kernel, and add the following code to the first notebook cell:</span></span>

        ```qsharp
        operation SayHello () : Unit {
            Message("Hello from quantum world!");
        }
        ```

    - <span data-ttu-id="f6487-119">Notebook のこのセルを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6487-119">Run this cell of the notebook:</span></span>

        ![Q # コードを含むセルを Jupyter Notebook](~/media/install-guide-jupyter.png)

        <span data-ttu-id="f6487-121">セルの出力に `SayHello` が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6487-121">You should see `SayHello` in the output of the cell.</span></span> <span data-ttu-id="f6487-122">Jupyter Notebook で実行すると、Q # コードがコンパイルされ、ノートブックによって検出された操作の名前が出力されます。</span><span class="sxs-lookup"><span data-stu-id="f6487-122">When running in Jupyter Notebook, the Q# code is compiled, and the notebook outputs the name of the operation(s) that it finds.</span></span>


    - <span data-ttu-id="f6487-123">新しいセルで、次のコマンドを使用して、先ほど作成した操作 (シミュレーター) を実行し `%simulate` ます。</span><span class="sxs-lookup"><span data-stu-id="f6487-123">In a new cell, execute the operation you just created (in a simulator) by using the `%simulate` command:</span></span>

        ![% シミュレートマジックを含むセルを Jupyter Notebook](~/media/install-guide-jupyter-simulate.png)

        <span data-ttu-id="f6487-125">画面には、呼び出された操作の結果と共に、メッセージが出力されます (ここでは、操作が単純に型を返すため、空のタプルが表示されて `()` `Unit` います)。</span><span class="sxs-lookup"><span data-stu-id="f6487-125">You should see the message printed on the screen along with the result of the operation you invoked (here, we see the empty tuple `()` because our operation simply returns a `Unit` type).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6487-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="f6487-126">Next steps</span></span>

<span data-ttu-id="f6487-127">Q # Jupyter Notebook 用の QDK をインストールしたので、Jupyter Notebook 環境内で直接 Q # コードを記述して、[最初のクォンタムプログラム](xref:microsoft.quantum.quickstarts.qrng)を作成して実行できます。</span><span class="sxs-lookup"><span data-stu-id="f6487-127">Now that you have installed the QDK for Q# Jupyter Notebooks, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng) by writing your Q# code directly within the Jupyter Notebook environment.</span></span>

<span data-ttu-id="f6487-128">Q # Jupyter Notebook でできることの詳細な例については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6487-128">For more examples of what you can do with Q# Jupyter Notebooks, please take a look at:</span></span>
- <span data-ttu-id="f6487-129">[Q # と Jupyter Notebook の概要を](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/)紹介します。</span><span class="sxs-lookup"><span data-stu-id="f6487-129">[Intro to Q# and Jupyter Notebook](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/).</span></span> <span data-ttu-id="f6487-130">ここでは、この環境で Q # を使用する方法を示す Q # Jupyter Notebook について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6487-130">There you will find a Q# Jupyter Notebook that shows how to use Q# in this environment.</span></span>
- <span data-ttu-id="f6487-131">[Quantum Katas](xref:microsoft.quantum.overview.katas)は、自習形式のチュートリアルのオープンソースのコレクションであり、Q # Jupyter notebook の形式でプログラミング演習を行います。</span><span class="sxs-lookup"><span data-stu-id="f6487-131">[Quantum Katas](xref:microsoft.quantum.overview.katas), an open-source collection of self-paced tutorials and sets of programming exercises in the form of Q# Jupyter Notebooks.</span></span> <span data-ttu-id="f6487-132">[Quantum Katas のチュートリアルノートブック](https://github.com/microsoft/QuantumKatas#tutorial-topics)は、出発点として適しています。</span><span class="sxs-lookup"><span data-stu-id="f6487-132">The [Quantum Katas tutorial notebooks](https://github.com/microsoft/QuantumKatas#tutorial-topics) are a good starting point.</span></span> <span data-ttu-id="f6487-133">Quantum Katas は、クォンタムコンピューティングと Q # プログラミングの要素を同時に教育することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="f6487-133">The Quantum Katas are aimed at teaching you elements of quantum computing and Q# programming at the same time.</span></span> <span data-ttu-id="f6487-134">これは、Q # Jupyter Notebook を使用して作成できるコンテンツの種類の優れた例です。</span><span class="sxs-lookup"><span data-stu-id="f6487-134">They're an excellent example of what kind of content you can create with Q# Jupyter Notebooks.</span></span>
