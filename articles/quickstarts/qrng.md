---
title: 量子乱数ジェネレーターの作成
description: 量子乱数ジェネレーターを作成することで、重ね合わせなど、基本的量子概念を実証する Q# プロジェクトを構築します。
author: bromeg
ms.author: megbrow@microsoft.com
ms.date: 10/25/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.qrng
ms.openlocfilehash: 8fafbccfe2a94a824353221b5e7eb8bac16c42f2
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327358"
---
# <a name="tutorial-implement-a-quantum-random-number-generator-in-q"></a><span data-ttu-id="1fa40-103">チュートリアル:Q\# で量子乱数ジェネレーターを実装する</span><span class="sxs-lookup"><span data-stu-id="1fa40-103">Tutorial: Implement a Quantum Random Number Generator in Q\#</span></span>

<span data-ttu-id="1fa40-104">Q# で記述された量子アルゴリズムの単純な例が量子乱数ジェネレーターです。</span><span class="sxs-lookup"><span data-stu-id="1fa40-104">A simple example of a quantum algorithm written in Q# is a quantum random number generator.</span></span> <span data-ttu-id="1fa40-105">このアルゴリズムでは、量子力学の性質を活用し、乱数を生成します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-105">This algorithm leverages the nature of quantum mechanics to produce a random number.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1fa40-106">前提条件</span><span class="sxs-lookup"><span data-stu-id="1fa40-106">Prerequisites</span></span>

- <span data-ttu-id="1fa40-107">Microsoft [Quantum 開発キット](xref:microsoft.quantum.install)。</span><span class="sxs-lookup"><span data-stu-id="1fa40-107">The Microsoft [Quantum Development Kit](xref:microsoft.quantum.install).</span></span>
- <span data-ttu-id="1fa40-108">[コマンド ラインから Q# を使用するため](xref:microsoft.quantum.install.standalone)、または [Python ホスト プログラム](xref:microsoft.quantum.install.python) または [C# ホスト プログラム](xref:microsoft.quantum.install.cs)で使用するために、Q# プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-108">Create a Q# project for either [using Q# from the command line](xref:microsoft.quantum.install.standalone), or with a [Python host program](xref:microsoft.quantum.install.python) or [C# host program](xref:microsoft.quantum.install.cs).</span></span>

## <a name="write-a-q-operation"></a><span data-ttu-id="1fa40-109">Q# 操作を記述する</span><span class="sxs-lookup"><span data-stu-id="1fa40-109">Write a Q# operation</span></span>

### <a name="q-operation-code"></a><span data-ttu-id="1fa40-110">Q# 操作コード</span><span class="sxs-lookup"><span data-stu-id="1fa40-110">Q# operation code</span></span>

1. <span data-ttu-id="1fa40-111">Program.qs ファイルの内容を次のコードに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-111">Replace the contents of the Program.qs file with the following code:</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-15,34":::

<span data-ttu-id="1fa40-112">「[量子コンピューティングについて](xref:microsoft.quantum.overview.understanding)」という記事で述べたように、キュービットとは、重ね合わせに入ることができる量子情報の単位です。</span><span class="sxs-lookup"><span data-stu-id="1fa40-112">As mentioned in our [Understanding quantum computing](xref:microsoft.quantum.overview.understanding) article, a qubit is a unit of quantum information that can be in superposition.</span></span> <span data-ttu-id="1fa40-113">測定されるとき、キュービットは 0 か 1 だけになります。</span><span class="sxs-lookup"><span data-stu-id="1fa40-113">When measured, a qubit can only be either 0 or 1.</span></span> <span data-ttu-id="1fa40-114">ただし、実行中、キュービットの状態は測定で 0 または 1 を読み取る可能性を表わします。</span><span class="sxs-lookup"><span data-stu-id="1fa40-114">However, during execution the state of the qubit represents the probability of reading either a 0 or a 1 with a measurement.</span></span> <span data-ttu-id="1fa40-115">この確率論的な状態が重ね合わせと呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="1fa40-115">This probabilistic state is known as superposition.</span></span> <span data-ttu-id="1fa40-116">この確率を使用し、乱数を生成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-116">We can use this probability to generate random numbers.</span></span>

<span data-ttu-id="1fa40-117">今回の Q# 操作では、Q# ネイティブの `Qubit` データ型を導入します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-117">In our Q# operation, we introduce the `Qubit` datatype, native to Q#.</span></span> <span data-ttu-id="1fa40-118">`Qubit` は `using` ステートメントでのみ割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-118">We can only allocate a `Qubit` with a `using` statement.</span></span> <span data-ttu-id="1fa40-119">割り当て後、キュービットは常に `Zero` 状態になります。</span><span class="sxs-lookup"><span data-stu-id="1fa40-119">When it gets allocated, a qubit is always in the `Zero`  state.</span></span> 

<span data-ttu-id="1fa40-120">`H` 操作を使用することで、`Qubit` を重ね合わせに入れることができます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-120">Using the `H` operation, we are able to put our `Qubit` in superposition.</span></span> <span data-ttu-id="1fa40-121">キュービットを測定し、その値を読み取るには、`M` 組み込み操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-121">To measure a qubit and read its value, you use the `M` intrinsic operation.</span></span>

<span data-ttu-id="1fa40-122">重ね合わせに `Qubit` を入れ、測定することで、コードを呼び出すたびに結果は異なる値になります。</span><span class="sxs-lookup"><span data-stu-id="1fa40-122">By putting our `Qubit` in superposition and measuring it, our result will be a different value each time the code is invoked.</span></span>

<span data-ttu-id="1fa40-123">`Qubit` の割り当てが解除されるとき、`Zero` 状態に明示的に戻す必要があります。戻さない場合、シミュレーターからランタイム エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-123">When a `Qubit` is de-allocated it must be explicitly set back to the `Zero` state, otherwise the simulator will report a runtime error.</span></span> <span data-ttu-id="1fa40-124">これを実現する簡単な方法は `Reset` を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="1fa40-124">An easy way to achieve this is invoking `Reset`.</span></span>

### <a name="visualizing-the-code-with-the-bloch-sphere"></a><span data-ttu-id="1fa40-125">ブロッホ球でコードを視覚化する</span><span class="sxs-lookup"><span data-stu-id="1fa40-125">Visualizing the code with the Bloch sphere</span></span>

<span data-ttu-id="1fa40-126">ブロッホ球では、北極は古典的な値 **0** を表し、南極は古典的な値 **1** を表します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-126">In the Bloch sphere, the north pole represents the classical value **0** and the south pole represents the classical value **1**.</span></span> <span data-ttu-id="1fa40-127">重ね合わせは球上の点で表わすことができます (矢印で表わされています)。</span><span class="sxs-lookup"><span data-stu-id="1fa40-127">Any superposition can be represented by a point on the sphere (represented by an arrow).</span></span> <span data-ttu-id="1fa40-128">矢印の端が極に近づけば近づくほど、測定時、その極に割り当てられる古典的な値にキュービットがなる確率が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1fa40-128">The closer the end of the arrow to a pole the higher the probability the qubit collapses into the classical value assigned to that pole when measured.</span></span> <span data-ttu-id="1fa40-129">たとえば、下の赤い矢印で表わされているキュービットの状態では、測定したとき、値 **0** が与えられる可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="1fa40-129">For example, the qubit state represented by the red arrow below has a higher probability of giving the value **0** if we measure it.</span></span>

<img src="~/media/qrng-Bloch.png" width="175" alt="A qubit state with a high probability of measuring zero">

<span data-ttu-id="1fa40-130">この表現を利用し、コードの動作を視覚化できます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-130">We can use this representation to visualize what the code is doing:</span></span>

* <span data-ttu-id="1fa40-131">まず、状態 **0** で初期化されたキュービットから始め、`H` を適用し、**0** と **1** の確率が同じになる重ね合わせを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-131">First we start with a qubit initialized in the state **0** and apply `H` to create a superposition in which the probabilities for **0** and **1** are the same.</span></span>

<img src="~/media/qrng-H.png" width="450" alt="Preparing a qubit in superposition">

* <span data-ttu-id="1fa40-132">次に、キュービットを測定し、出力を保存します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-132">Then we measure the qubit and save the output:</span></span>

<img src="~/media/qrng-meas.png" width="450" alt="Measuring a qubit and saving the output">

<span data-ttu-id="1fa40-133">測定の結果は完全にランダムになるため、ランダム ビットが 1 つ取得されました。</span><span class="sxs-lookup"><span data-stu-id="1fa40-133">Since the outcome of the measurement is completely random, we have obtained a random bit.</span></span> <span data-ttu-id="1fa40-134">この操作を複数回呼び出し、整数を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-134">We can call this operation several times to create integers.</span></span> <span data-ttu-id="1fa40-135">たとえば、操作を 3 回呼び出してランダム ビットを 3 つ取得する場合、ランダムの 3 ビット数 (つまり、0 から 7 までの乱数) を構築できます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-135">For example, if we call the operation three times to obtain three random bits, we can build random 3-bit numbers (that is, a random number between 0 and 7).</span></span>


## <a name="creating-a-complete-random-number-generator"></a><span data-ttu-id="1fa40-136">完全な乱数ジェネレーターの作成</span><span class="sxs-lookup"><span data-stu-id="1fa40-136">Creating a complete random number generator</span></span>

<span data-ttu-id="1fa40-137">ランダム ビットを生成する Q# 操作ができたので、それを使用して、完全な量子乱数ジェネレーターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-137">Now that we have a Q# operation that generates random bits, we can use it to build a complete quantum random number generator.</span></span> <span data-ttu-id="1fa40-138">Q# コマンド ライン アプリケーションを使用することも、ホスト プログラムを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-138">We can use the Q# command line applications or use a host program.</span></span>



### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>[<span data-ttu-id="1fa40-139">Visual Studio または Visual Studio Code を使用する Q# コマンド ライン アプリケーション</span><span class="sxs-lookup"><span data-stu-id="1fa40-139">Q# command line applications with Visual Studio or Visual Studio Code</span></span>](#tab/tabid-qsharp)

<span data-ttu-id="1fa40-140">完全な Q# コマンドライン アプリケーションを作成するには、使用する Q# プログラムに次のエントリ ポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-140">To create the full Q# command line application, add the following entry point to your Q# program:</span></span> 

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="17-33":::

<span data-ttu-id="1fa40-141">実行可能ファイルは、プロジェクトの構成とコマンドライン オプションに応じて、シミュレーターまたはリソース推定機能で `@EntryPoint()` 属性でマークされた操作または関数を実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-141">The executable will run the operation or function marked with the `@EntryPoint()` attribute on a simulator or resource estimator, depending on the project configuration and command-line options.</span></span>

:::code language="qsharp" source="~/quantum/samples/getting-started/qrng/Qrng.qs" range="3-34":::

<span data-ttu-id="1fa40-142">Visual Studio では、Ctrl キーを押しながら F5 キーを押すだけでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-142">In Visual Studio, simply press Ctrl + F5 to execute the script.</span></span>

<span data-ttu-id="1fa40-143">VS Code では、ターミナルで次のように入力して、Program.qs の初回のビルドを行います。</span><span class="sxs-lookup"><span data-stu-id="1fa40-143">In VS Code, build the Program.qs the first time by typing the below in the terminal:</span></span>

```dotnetcli
dotnet build
```

<span data-ttu-id="1fa40-144">以降の実行では、再度ビルドする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1fa40-144">For subsequent runs, there is no need to build it again.</span></span> <span data-ttu-id="1fa40-145">これを実行するには、次のコマンドを入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-145">To run it, type the following command and press enter:</span></span>

```dotnetcli
dotnet run --no-build
```

### <a name="python-with-visual-studio-code-or-the-command-line"></a>[<span data-ttu-id="1fa40-146">Visual Studio Code またはコマンド ラインを使用した Python</span><span class="sxs-lookup"><span data-stu-id="1fa40-146">Python with Visual Studio Code or the Command Line</span></span>](#tab/tabid-python)

<span data-ttu-id="1fa40-147">Python から新しい Q# プログラムを実行するには、次のコードを `host.py` として保存します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-147">To run your new Q# program from Python, save the following code as `host.py`:</span></span>

:::code language="python" source="~/quantum/samples/interoperability/qrng/host.py" range="11-30":::

<span data-ttu-id="1fa40-148">次に、コマンド ラインから Python ホスト プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="1fa40-148">You can then run your Python host program from the command line:</span></span>

```bash
$ python host.py
Preparing Q# environment...
..The random number generated is 42
```

### <a name="c-with-visual-studio-code-or-visual-studio"></a>[<span data-ttu-id="1fa40-149">Visual Studio Code または Visual Studio を使用する C#</span><span class="sxs-lookup"><span data-stu-id="1fa40-149">C# with Visual Studio Code or Visual Studio</span></span>](#tab/tabid-csharp)

<span data-ttu-id="1fa40-150">C# から新しい Q# プログラムを実行するには、次の C# コードを含めるように `Driver.cs` を変更します。</span><span class="sxs-lookup"><span data-stu-id="1fa40-150">To run your new Q# program from C#, modify `Driver.cs` to include the following C# code:</span></span>

:::code language="csharp" source="~/quantum/samples/interoperability/qrng/Host.cs" range="4-39":::

<span data-ttu-id="1fa40-151">次に、コマンド ラインから C# ホスト プログラムを実行できます (Visual Studio では、F5 キーを押す必要があります)。</span><span class="sxs-lookup"><span data-stu-id="1fa40-151">You can then run your C# host program from the command line (in Visual Studio you should press F5):</span></span>

```bash
$ dotnet run
The random number generated is 42
```

***
