---
title: 量子乱数ジェネレーターの作成
description: 量子乱数ジェネレーターを作成することで、重ね合わせなど、基本的量子概念を実証する Q# プロジェクトを構築します。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: d1ad2c1153814e2fa19a38307b2c668c77eae4e3
ms.sourcegitcommit: b7e205aaa7fa1ca9f0daa163e46154945f4bc965
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2020
ms.locfileid: "77441073"
---
# <a name="quickstart-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="8a8cc-103">クイック スタート:Q# で量子乱数ジェネレーターを実装する</span><span class="sxs-lookup"><span data-stu-id="8a8cc-103">Quickstart: Implement a Quantum Random Number Generator in Q#</span></span>
<span data-ttu-id="8a8cc-104">Q# で記述された量子アルゴリズムの単純な例が量子乱数ジェネレーターです。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="8a8cc-105">このアルゴリズムでは、量子力学の性質を活用し、乱数を生成します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8a8cc-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="8a8cc-106">Prerequisites</span></span>

- <span data-ttu-id="8a8cc-107">Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- [<span data-ttu-id="8a8cc-108">Q# プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="8a8cc-108">Create a Q# Project</span></span>](xref:microsoft.quantum.howto.createproject)


## <a name="write-a-q-operation"></a><span data-ttu-id="8a8cc-109">Q# 操作を記述する</span><span class="sxs-lookup"><span data-stu-id="8a8cc-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="8a8cc-110">Q# 操作コード</span><span class="sxs-lookup"><span data-stu-id="8a8cc-110">Q# operation code</span></span>

1. <span data-ttu-id="8a8cc-111">Operation.qs ファイルの内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-111">Replace the contents of the Operation.qs file with the following code:</span></span>

 :::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-14":::

<span data-ttu-id="8a8cc-112">「[量子コンピューティングとは](xref:microsoft.quantum.overview.what)」という記事で述べたように、キュービットとは、重ね合わせに入ることができる量子情報の単位です。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-112">As mentioned in our [What is Quantum Computing?](xref:microsoft.quantum.overview.what) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="8a8cc-113">測定されるとき、キュービットは 0 か 1 だけになります。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="8a8cc-114">ただし、実行中、キュービットの状態は測定で 0 または 1 を読み取る可能性を表わします。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="8a8cc-115">この確率論的な状態が重ね合わせと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="8a8cc-116">この確率を使用し、乱数を生成できます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="8a8cc-117">今回の Q# 操作では、Q# ネイティブの `Qubit` データ型を導入します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="8a8cc-118">`Qubit` は `using` ステートメントでのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="8a8cc-119">割り当て後、キュービットは常に `Zero` 状態になります。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="8a8cc-120">`H` 操作を使用することで、`Qubit` を重ね合わせに入れることができます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="8a8cc-121">キュービットを測定し、その値を読み取るには、`M` 組み込み操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="8a8cc-122">重ね合わせに `Qubit` を入れ、測定することで、コードを呼び出すたびに結果は異なる値になります。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span> 

<span data-ttu-id="8a8cc-123">`Qubit` の割り当てが解除されるとき、`Zero` 状態に明示的に戻す必要があります。戻さない場合、シミュレーターからランタイム エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="8a8cc-124">これを実現する簡単な方法は `Reset` を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="8a8cc-125">ブロッホ球でコードを視覚化する</span><span class="sxs-lookup"><span data-stu-id="8a8cc-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="8a8cc-126">ブロッホ球では、北極は古典的な値 **0** を表し、南極は古典的な値 **1** を表します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="8a8cc-127">重ね合わせは球上の点で表わすことができます (矢印で表わされています)。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="8a8cc-128">矢印の端が極に近づけば近づくほど、測定時、その極に割り当てられる古典的な値にキュービットがなる確率が高くなります。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="8a8cc-129">たとえば、下の赤い矢印で表わされているキュービットの状態では、測定したとき、値 **0** が与えられる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175">

<span data-ttu-id="8a8cc-130">この表現を利用し、コードの動作を視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="8a8cc-131">まず、状態 **0** で初期化されたキュービットから始め、`H` を適用し、**0** と **1** の確率が同じになる重ね合わせを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-131">First we start with a qubit initalizated in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450">

* <span data-ttu-id="8a8cc-132">次に、キュービットを測定し、出力を保存します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450">

<span data-ttu-id="8a8cc-133">測定の結果は完全にランダムになるため、ランダム ビットが 1 つ取得されました。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="8a8cc-134">この操作を複数回呼び出し、整数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="8a8cc-135">たとえば、操作を 3 回呼び出してランダム ビットを 3 つ取得する場合、ランダムの 3 ビット数 (つまり、0 から 7 までの乱数) を構築できます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>

## <a name="creating-a-complete-random-number-generator-using-a-host-program"></a><span data-ttu-id="8a8cc-136">ホスト プログラムを使用した完全な乱数ジェネレーターを作成する</span><span class="sxs-lookup"><span data-stu-id="8a8cc-136">Creating a complete random number generator using a host program</span></span>

<span data-ttu-id="8a8cc-137">ランダム ビットを生成する Q # 操作ができたので、それを使用して、ホスト プログラムを使用した完全な量子乱数ジェネレーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator with a host program.</span></span>

 ### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="8a8cc-138">Visual Studio Code またはコマンド ラインを使用した Python</span><span class="sxs-lookup"><span data-stu-id="8a8cc-138">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)
 
 <span data-ttu-id="8a8cc-139">Python から新しい Q# プログラムを実行するには、次のコードを `host.py` として保存します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-139">To run your new Q# program from Python, save the following code as `host.py`:</span></span>
 
:::code language="python" source="~/quantum/samples/getting-started/qrng/host.py" range="11-30":::

 <span data-ttu-id="8a8cc-140">次に、コマンド ラインから Python ホスト プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-140">You can then run your Python host program from the command line:</span></span>
 ```bash
 $ python host.py
 Preparing Q# environment...
 ..The random number generated is 42
 ```
 ### <a name="c-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="8a8cc-141">Visual Studio Code またはコマンド ラインを使用した C#</span><span class="sxs-lookup"><span data-stu-id="8a8cc-141">C# with Visual Studio Code or the Command Line</span></span>](#tab/tabid-csharp)
 
 <span data-ttu-id="8a8cc-142">C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-142">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>
 
 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::
 
 <span data-ttu-id="8a8cc-143">次に、コマンド ラインから C# ホスト プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-143">You can then run your C# host program from the command line:</span></span>
 
 ```bash
 $ dotnet run
 The random number generated is 42
 ```

 ### <a name="c-with-visual-studio-2019"></a>[<span data-ttu-id="8a8cc-144">Visual Studio 2019 を使用した C#</span><span class="sxs-lookup"><span data-stu-id="8a8cc-144">C# with Visual Studio 2019</span></span>](#tab/tabid-vs2019)

 <span data-ttu-id="8a8cc-145">Visual Studio で C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-145">To run your new Q# program from C# in Visual Studio, modify `Driver.cs` to include the following C# code:</span></span>

 :::code language="csharp" source="~/quantum/samples/getting-started/qrng/Host.cs" range="4-39":::

 <span data-ttu-id="8a8cc-146">その後、F5 キーを押すと、プログラムは実行を開始し、乱数が生成されている新しいウィンドウがポップアップ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a8cc-146">Then press F5, the program will start execution and a new window will pop up with the random number generated:</span></span> 

 ```bash
 $ dotnet run
 The random number generated is 42
 ```
 ***
