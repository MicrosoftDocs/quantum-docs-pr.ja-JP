---
title: クォンタム Machine Learning ライブラリを使用した基本的な分類
description: Q#Microsoft QDK の quantum Machine Learning ライブラリを使用して、で記述されたクォンタムシーケンシャル分類器を実行する方法について説明します。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: f9c3e7ab85c0f0d1a6063e593607d35c5cb76936
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868969"
---
# <a name="basic-classification-classify-data-with-the-qdk"></a><span data-ttu-id="a459d-103">基本分類: QDK でデータを分類する</span><span class="sxs-lookup"><span data-stu-id="a459d-103">Basic classification: Classify data with the QDK</span></span>

<span data-ttu-id="a459d-104">このクイックスタートでは、で記述されたクォンタムシーケンシャル分類器を実行する方法につい Q# Machine Learning て説明します。</span><span class="sxs-lookup"><span data-stu-id="a459d-104">In this Quickstart, you will learn how to execute a quantum sequential classifier written in Q# using the Quantum Machine Learning library of the QDK.</span></span> 

<span data-ttu-id="a459d-105">このガイドでは、「」で定義されている分類子構造を使用して、半月のデータセットを使用し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="a459d-105">In this guide we will use the half-moon dataset, using a classifier structure defined in Q#.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a459d-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="a459d-106">Prerequisites</span></span>

- <span data-ttu-id="a459d-107">Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="a459d-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="a459d-108">Q# [Python ホストプログラム](xref:microsoft.quantum.install.python)または[C# ホストプログラム](xref:microsoft.quantum.install.cs)のいずれかのプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a459d-108">Create a Q# project for either a [Python host program](xref:microsoft.quantum.install.python) or a [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="host-program"></a><span data-ttu-id="a459d-109">ホストプログラム</span><span class="sxs-lookup"><span data-stu-id="a459d-109">Host program</span></span>

<span data-ttu-id="a459d-110">ホストプログラムは、次の3つの部分で構成されます。</span><span class="sxs-lookup"><span data-stu-id="a459d-110">Your host program consists of three parts:</span></span>

- <span data-ttu-id="a459d-111">データセットを読み込み、モデルの開始パラメーターのセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="a459d-111">Load the dataset and choose a set of starting parameters for your model.</span></span>
- <span data-ttu-id="a459d-112">トレーニングを実行して、モデルのパラメーターとバイアスを決定します。</span><span class="sxs-lookup"><span data-stu-id="a459d-112">Execute training to determine the parameters and bias of the model.</span></span>
- <span data-ttu-id="a459d-113">モデルを検証してその精度を確認する</span><span class="sxs-lookup"><span data-stu-id="a459d-113">Validate the model to determine its accuracy</span></span>

    ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="a459d-114">Visual Studio Code またはコマンド ラインを使用した Python</span><span class="sxs-lookup"><span data-stu-id="a459d-114">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

    <span data-ttu-id="a459d-115">Python の分類子であるを実行するには、 Q# 次のコードをとして保存し `host.py` ます。</span><span class="sxs-lookup"><span data-stu-id="a459d-115">To run your the Q# classifier from Python, save the following code as `host.py`.</span></span> <span data-ttu-id="a459d-116">Q# `Training.qs` このチュートリアルの後半で説明するファイルも必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a459d-116">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="3-42":::

    <span data-ttu-id="a459d-117">次に、コマンド ラインから Python ホスト プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a459d-117">You can then run your Python host program from the command line:</span></span>

    ```bash
    $ python host.py
    Preparing Q# environment...
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="a459d-118">Visual Studio Code またはコマンド ラインを使用した C#</span><span class="sxs-lookup"><span data-stu-id="a459d-118">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)

    <span data-ttu-id="a459d-119">C# の分類子であるを実行するには、 Q# 次のコードをとして保存し `Host.cs` ます。</span><span class="sxs-lookup"><span data-stu-id="a459d-119">To run your the Q# classifier from C#, save the following code as `Host.cs`.</span></span> <span data-ttu-id="a459d-120">Q# `Training.qs` このチュートリアルの後半で説明するファイルも必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a459d-120">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="a459d-121">次に、コマンド ラインから C# ホスト プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a459d-121">You can then run your C# host program from the command line:</span></span>

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```

    ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="a459d-122">Visual Studio 2019 を使用した C#</span><span class="sxs-lookup"><span data-stu-id="a459d-122">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

    <span data-ttu-id="a459d-123">Q#Visual Studio で c# から新しいプログラムを実行するには、 `Host.cs` 次の c# コードを含むようにを変更します。</span><span class="sxs-lookup"><span data-stu-id="a459d-123">To run your new Q# program from C# in Visual Studio, modify `Host.cs` to include the following C# code.</span></span> <span data-ttu-id="a459d-124">Q# `Training.qs` このチュートリアルの後半で説明するファイルも必要であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a459d-124">Remember that you also need the Q# file `Training.qs` that is explained later in this tutorial.</span></span>

    :::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="4-86":::

    <span data-ttu-id="a459d-125">F5 キーを押すと、プログラムは実行を開始し、新しいポップアップ ウィンドウに次の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a459d-125">Then press F5, the program will start execution and a new windows will pop-up with the following results:</span></span> 

    ```bash
    $ dotnet run
    [...]
    Observed X.XX% misclassifications.
    ```
    ***

## <a name="q-classifier-code"></a><span data-ttu-id="a459d-126">Q \# 分類器コード</span><span class="sxs-lookup"><span data-stu-id="a459d-126">Q\# classifier code</span></span>

<span data-ttu-id="a459d-127">次に、ホストプログラムによって呼び出された操作がでどのように定義されているかを見てみましょう Q# 。</span><span class="sxs-lookup"><span data-stu-id="a459d-127">Now let's see how the operations invoked by the host program are defined in Q#.</span></span>
<span data-ttu-id="a459d-128">次のコードをという名前のファイルに保存 `Training.qs` します。</span><span class="sxs-lookup"><span data-stu-id="a459d-128">We save the following code in a file named `Training.qs`.</span></span>

:::code language="qsharp" source="~/quantum/samples/machine-learning/half-moons/Training.qs" range="4-116":::

<span data-ttu-id="a459d-129">上記のコードで定義されている最も重要な関数と操作は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a459d-129">The most important functions and operations defined in the code above are:</span></span>

- <span data-ttu-id="a459d-130">`ClassifierStructure() : ControlledRotation[]`: この関数では、考慮する制御ゲートのレイヤーを追加することによって、サーキットモデルの構造を設定します。</span><span class="sxs-lookup"><span data-stu-id="a459d-130">`ClassifierStructure() : ControlledRotation[]` : in this function we set the structure of our circuit model by adding the layers of the controlled gates we consider.</span></span> <span data-ttu-id="a459d-131">この手順は、シーケンシャルなディープラーニングモデルでのニューロンのレイヤーの宣言に似ています。</span><span class="sxs-lookup"><span data-stu-id="a459d-131">This step is analogous to the declaration of layers of neurons in a sequential deep learning model.</span></span>
- <span data-ttu-id="a459d-132">`TrainHalfMoonModel() : (Double[], Double)`: この操作はコードの中核となる部分で、トレーニングを定義します。</span><span class="sxs-lookup"><span data-stu-id="a459d-132">`TrainHalfMoonModel() : (Double[], Double)` : this operation is the core part of the code and defines the training.</span></span> <span data-ttu-id="a459d-133">ここでは、ライブラリに含まれるデータセットからサンプルを読み込みます。ここでは、トレーニングのハイパーパラメーターと初期パラメーターを設定し、ライブラリに含まれる操作を呼び出してトレーニングを開始し `TrainSequentialClassifier` ます。</span><span class="sxs-lookup"><span data-stu-id="a459d-133">Here we load the samples from the dataset included in the library, we set the hyper parameters and the initial parameters for the training and we start the training by calling the operation `TrainSequentialClassifier` included in the library.</span></span> <span data-ttu-id="a459d-134">パラメーターと、分類子を決定するバイアスを出力します。</span><span class="sxs-lookup"><span data-stu-id="a459d-134">It outputs the parameters and the bias that determine the classifier.</span></span>
- <span data-ttu-id="a459d-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int`: この操作では、モデルを評価するための検証プロセスを定義します。</span><span class="sxs-lookup"><span data-stu-id="a459d-135">`ValidateHalfMoonModel(parameters : Double[], bias : Double) : Int` : this operation defines the validation process to evaluate the model.</span></span> <span data-ttu-id="a459d-136">ここでは、検証用のサンプル、サンプルごとの測定数、および許容範囲を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="a459d-136">Here we load the samples for validation, the number of measurements per sample and the tolerance.</span></span> <span data-ttu-id="a459d-137">検証用に選択されたサンプルのバッチに誤分類の数が出力されます。</span><span class="sxs-lookup"><span data-stu-id="a459d-137">It outputs the number of misclassifications on the chosen batch of samples for validation.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a459d-138">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a459d-138">Next steps</span></span>

<span data-ttu-id="a459d-139">まず、コードを使用して再生し、いくつかのパラメーターを変更してトレーニングにどのように影響するかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a459d-139">First, you can play with the code and try to change some parameters to see how it affects the training.</span></span> <span data-ttu-id="a459d-140">次のチュートリアル「[独自の分類子の設計](xref:microsoft.quantum.libraries.machine-learning.design)」では、分類子の構造を定義する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="a459d-140">Then, in the next tutorial, [Design your own classifier](xref:microsoft.quantum.libraries.machine-learning.design),  you will learn how to define the structure of the classifier.</span></span>
