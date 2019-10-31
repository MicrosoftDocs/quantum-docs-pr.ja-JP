---
title: 量子シミュレーターと従来型のドライバー | Microsoft Docs
description: 従来型のコンピューティング .NET 言語 (通常 C# または Q#) を使用して量子シミュレーターを実行する方法について説明します。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines
ms.openlocfilehash: 5ac79280669ae0acfe993a1c2ae1c069b0c01848
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035113"
---
# <a name="classical-drivers-and-machines"></a><span data-ttu-id="c8aff-103">従来型のドライバーとコンピューター</span><span class="sxs-lookup"><span data-stu-id="c8aff-103">Classical Drivers and Machines</span></span>

## <a name="what-youll-learn"></a><span data-ttu-id="c8aff-104">ここでは、次の内容について学習します</span><span class="sxs-lookup"><span data-stu-id="c8aff-104">What You'll Learn</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="c8aff-105">量子アルゴリズムの実行方法</span><span class="sxs-lookup"><span data-stu-id="c8aff-105">How quantum algorithms are executed</span></span>
> * <span data-ttu-id="c8aff-106">このリリースに含まれる量子シミュレーターについて</span><span class="sxs-lookup"><span data-stu-id="c8aff-106">What quantum simulators are included in this release</span></span>
> * <span data-ttu-id="c8aff-107">量子アルゴリズムの C# ドライバーを記述する方法</span><span class="sxs-lookup"><span data-stu-id="c8aff-107">How to write a C# driver for your quantum algorithm</span></span>

## <a name="the-quantum-development-kit-execution-model"></a><span data-ttu-id="c8aff-108">Quantum Development Kit の実行モデル</span><span class="sxs-lookup"><span data-stu-id="c8aff-108">The Quantum Development Kit Execution Model</span></span>

<span data-ttu-id="c8aff-109">[量子プログラムを記述する](xref:microsoft.quantum.write-program)方法に関する記事では、`QuantumSimulator` オブジェクトをアルゴリズム クラスの `Run` メソッドに渡すことによって、量子アルゴリズムを実行しました。</span><span class="sxs-lookup"><span data-stu-id="c8aff-109">In [Writing a quantum program](xref:microsoft.quantum.write-program), we executed our quantum algorithm by passing a `QuantumSimulator` object to the algorithm class's `Run` method.</span></span>
<span data-ttu-id="c8aff-110">`QuantumSimulator` クラスは、`Teleport` の実行とテストに最適な量子状態ベクトルを完全にシミュレートすることで、量子アルゴリズムを実行します。</span><span class="sxs-lookup"><span data-stu-id="c8aff-110">The `QuantumSimulator` class executes the quantum algorithm by fully simulating the quantum state vector, which is perfect for running and testing `Teleport`.</span></span>
<span data-ttu-id="c8aff-111">量子状態ベクトルの詳細については、[概念に関するガイド](xref:microsoft.quantum.concepts.intro)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c8aff-111">See the [Concepts guide](xref:microsoft.quantum.concepts.intro) for more on quantum state vectors.</span></span>

<span data-ttu-id="c8aff-112">他のターゲット コンピューターを使用して、量子アルゴリズムを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-112">Other target machines may be used to run a quantum algorithm.</span></span>
<span data-ttu-id="c8aff-113">このコンピューターは、アルゴリズムに対して量子プリミティブを実装する役割を担います。</span><span class="sxs-lookup"><span data-stu-id="c8aff-113">The machine is responsible for providing implementations of quantum primitives for the algorithm.</span></span>
<span data-ttu-id="c8aff-114">これには、H、CNOT、Measure などのプリミティブ操作だけでなく、量子ビットの管理と追跡も含まれます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-114">This includes primitive operations such as H, CNOT, and Measure, as well as qubit management and tracking.</span></span>
<span data-ttu-id="c8aff-115">異なるクラスの量子コンピューターは、同じ量子アルゴリズムの異なる実行モデルを表します。</span><span class="sxs-lookup"><span data-stu-id="c8aff-115">Different classes of quantum machines represent different execution models for the same quantum algorithm.</span></span>

<span data-ttu-id="c8aff-116">量子コンピュータ－は、種類に応じてこのようなプリミティブの異なる実装を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-116">Each type of quantum machine may provide different implementations of these primitives.</span></span>
<span data-ttu-id="c8aff-117">たとえば、開発キットに含まれている量子コンピューターのトレース シミュレーターは、シミュレーション一切行いません。</span><span class="sxs-lookup"><span data-stu-id="c8aff-117">For instance, the quantum computer trace simulator included in the development kit doesn't do any simulation at all.</span></span>
<span data-ttu-id="c8aff-118">代わりに、アルゴリズムのゲート、量子ビット、およびその他のリソースの使用状況を追跡します。</span><span class="sxs-lookup"><span data-stu-id="c8aff-118">Rather, it tracks gate, qubit, and other resource usage for the algorithm.</span></span>

### <a name="quantum-machines"></a><span data-ttu-id="c8aff-119">量子コンピューター</span><span class="sxs-lookup"><span data-stu-id="c8aff-119">Quantum Machines</span></span>

<span data-ttu-id="c8aff-120">今後、他の種類のシミュレーションや、トポロジカル量子コンピューターでの実行をサポートするために、追加の量子コンピューター クラスを定義する予定です。</span><span class="sxs-lookup"><span data-stu-id="c8aff-120">In the future, we will define additional quantum machine classes to support other types of simulation and to support execution on topological quantum computers.</span></span>
<span data-ttu-id="c8aff-121">基になるコンピューターの実装を変更してもアルゴリズムが一定に保たれるようにすることで、シミュレーションのアルゴリズムのテストとデバッグが簡単になり、アルゴリズムが変更されていないという確信を持って実際のハードウェアで実行できます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-121">Allowing the algorithm to stay constant while varying the underlying machine implementation makes it easy to test and debug an algorithm in simulation and then run it on real hardware with confidence that the algorithm hasn't changed.</span></span>

### <a name="whats-included-in-this-release"></a><span data-ttu-id="c8aff-122">このリリースの新機能は次のとおりです</span><span class="sxs-lookup"><span data-stu-id="c8aff-122">What's Included in this Release</span></span>

<span data-ttu-id="c8aff-123">このリリースの量子開発者キットには、いくつかの量子コンピューター クラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c8aff-123">This release of the quantum developer kit includes several quantum machine classes.</span></span>
<span data-ttu-id="c8aff-124">すべてのクラスは、`Microsoft.Quantum.Simulation.Simulators` 名前空間で定義されています。</span><span class="sxs-lookup"><span data-stu-id="c8aff-124">All of them are defined in the `Microsoft.Quantum.Simulation.Simulators` namespace.</span></span>

* <span data-ttu-id="c8aff-125">`QuantumSimulator` クラスの[完全状態ベクトル シミュレーター](xref:microsoft.quantum.machines.full-state-simulator)。</span><span class="sxs-lookup"><span data-stu-id="c8aff-125">A [full state vector simulator](xref:microsoft.quantum.machines.full-state-simulator), the `QuantumSimulator` class.</span></span>
* <span data-ttu-id="c8aff-126">`ResourcesEstimator` クラスの[簡易リソース推定機能](xref:microsoft.quantum.machines.resources-estimator)を使用すると、量子アルゴリズムを実行するために必要なリソースを最上位レベルで分析できます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-126">A [simple resources estimator](xref:microsoft.quantum.machines.resources-estimator), the `ResourcesEstimator` class, it allows a top level analysis of the resources needed to run a quantum algorithm.</span></span>
* <span data-ttu-id="c8aff-127">`QCTraceSimulator` クラスの[トレース ベースのリソース推定機能](xref:microsoft.quantum.machines.qc-trace-simulator.intro)を使用すると、アルゴリズムの呼び出しグラフ全体におけるリソース消費の高度な分析を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-127">A [trace-based resource estimator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), the `QCTraceSimulator` class, it allows advanced analysis of resources consumptions for the algorithm's entire call-graph.</span></span>
* <span data-ttu-id="c8aff-128">`ToffoliSimulator` クラスの [Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)。</span><span class="sxs-lookup"><span data-stu-id="c8aff-128">A [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator), the `ToffoliSimulator` class.</span></span>

## <a name="writing-a-classical-driver-program"></a><span data-ttu-id="c8aff-129">Classical Driver Program を作成する</span><span class="sxs-lookup"><span data-stu-id="c8aff-129">Writing a Classical Driver Program</span></span>

<span data-ttu-id="c8aff-130">[量子プログラムを記述する方法](xref:microsoft.quantum.write-program)に関する記事では、テレポート アルゴリズムの単純な C# ドライバーを記述しました。</span><span class="sxs-lookup"><span data-stu-id="c8aff-130">In [Writing a quantum program](xref:microsoft.quantum.write-program), we wrote a simple C# driver for our teleport algorithm.</span></span> <span data-ttu-id="c8aff-131">C# ドライバーには主に次の 4 つの目的があります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-131">A C# driver has 4 main purposes:</span></span>

* <span data-ttu-id="c8aff-132">ターゲット コンピューターの構築</span><span class="sxs-lookup"><span data-stu-id="c8aff-132">Constructing the target machine</span></span>
* <span data-ttu-id="c8aff-133">量子アルゴリズムに必要な引数の計算</span><span class="sxs-lookup"><span data-stu-id="c8aff-133">Computing any arguments required for the quantum algorithm</span></span>
* <span data-ttu-id="c8aff-134">シミュレーターを使用した量子アルゴリズムの実行</span><span class="sxs-lookup"><span data-stu-id="c8aff-134">Running the quantum algorithm using the simulator</span></span>
* <span data-ttu-id="c8aff-135">操作の結果の処理</span><span class="sxs-lookup"><span data-stu-id="c8aff-135">Processing the result of the operation</span></span>

<span data-ttu-id="c8aff-136">ここでは、各手順について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c8aff-136">Here we'll discuss each step in more detail.</span></span>

### <a name="constructing-the-target-machine"></a><span data-ttu-id="c8aff-137">ターゲット コンピューターを構築する</span><span class="sxs-lookup"><span data-stu-id="c8aff-137">Constructing the Target Machine</span></span>

<span data-ttu-id="c8aff-138">量子コンピュータ－は通常の .NET クラスのインスタンスであるため、.NET クラスと同様に、コンストラクターを呼び出すことによって作成します。</span><span class="sxs-lookup"><span data-stu-id="c8aff-138">Quantum machines are instances of normal .NET classes, so they are created by invoking their constructor, just like any .NET class.</span></span>
<span data-ttu-id="c8aff-139">`QuantumSimulator` を含む一部のシミュレーターは .NET <xref:System.IDisposable?displayProperty=nameWithType> インターフェイスを実装するため、C# `using` ステートメントでラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-139">Some simulators, including the `QuantumSimulator`, implement the .NET <xref:System.IDisposable?displayProperty=nameWithType> interface, and so should be wrapped in a C# `using` statement.</span></span>

### <a name="computing-arguments-for-the-algorithm"></a><span data-ttu-id="c8aff-140">アルゴリズムの引数を計算する</span><span class="sxs-lookup"><span data-stu-id="c8aff-140">Computing Arguments for the Algorithm</span></span>

<span data-ttu-id="c8aff-141">`Teleport` の例では、量子アルゴリズムに渡す比較的人工的な引数をいくつか計算しています。</span><span class="sxs-lookup"><span data-stu-id="c8aff-141">In our `Teleport` example, we computed some relatively artificial arguments to pass to our quantum algorithm.</span></span>
<span data-ttu-id="c8aff-142">ただし、通常は、量子アルゴリズムで重要なデータが必要とされるため、従来型のドライバーから取得するのが最も簡単です。</span><span class="sxs-lookup"><span data-stu-id="c8aff-142">More typically, however, there is significant data required by the quantum algorithm, and it is easiest to provide it from the classical driver.</span></span>

<span data-ttu-id="c8aff-143">たとえば、量子アルゴリズムで化学シミュレーションを実行する場合、分子軌道相互作用の数値を示す大きなテーブルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c8aff-143">For instance, when doing chemical simulations, the quantum algorithm requires a large table of molecular orbital interaction integrals.</span></span>
<span data-ttu-id="c8aff-144">通常、このようなテーブルはアルゴリズムの実行時に提供されるファイルから読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-144">Generally these are read in from a file that is provided when running the algorithm.</span></span>
<span data-ttu-id="c8aff-145">Q# にはファイル システムにアクセスするためのメカニズムがないため、この種のデータは従来型のドライバーによって収集され、量子アルゴリズムの `Run` メソッドに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-145">Since Q# does not have a mechanism for accessing the file system, this sort of data is best collected by the classical driver and then passed to the quantum algorithm's `Run` method.</span></span>

<span data-ttu-id="c8aff-146">従来型のドライバーが主要な役割を果たすもう 1 つの場合があります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-146">Another case where the classical driver plays a key role is in variational methods.</span></span>
<span data-ttu-id="c8aff-147">このクラスのアルゴリズムでは、一部の従来型のパラメーターに基づいて量子状態が準備され、値の計算にはその状態が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-147">In this class of algorithms, a quantum state is prepared based on some classical parameters, and that state is used to compute some value of interest.</span></span>
<span data-ttu-id="c8aff-148">このパラメーターは、何らかの山登り法または機械学習アルゴリズムに基づいて調整され、その後、量子アルゴリズムは再度実行されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-148">The parameters are adjusted based on some type of hill climbing or machine learning algorithm and the quantum algorithm run again.</span></span>
<span data-ttu-id="c8aff-149">このようなアルゴリズムでは、山登り法アルゴリズム自体を、従来型のドライバーによって呼び出される純粋な関数として実装することをお勧めします。その後、山登り法による結果は、次に実行される量子アルゴリズムに渡されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-149">For such algorithms, the hill climbing algorithm itself is best implemented as a purely classical function that is called by the classical driver; the results of the hill climbing are then passed to the next execution of the quantum algorithm.</span></span>

### <a name="running-the-quantum-algorithm"></a><span data-ttu-id="c8aff-150">量子アルゴリズムを実行する</span><span class="sxs-lookup"><span data-stu-id="c8aff-150">Running the Quantum Algorithm</span></span>

<span data-ttu-id="c8aff-151">このパートの大部分は、きわめて単純です。</span><span class="sxs-lookup"><span data-stu-id="c8aff-151">This part is generally very straightforward.</span></span>
<span data-ttu-id="c8aff-152">各 Q# 操作は、静的な `Run` メソッドを提供するクラスにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-152">Each Q# operation is compiled into a class that provides a static `Run` method.</span></span>
<span data-ttu-id="c8aff-153">このメソッドへの引数は、操作自体のフラット化された引数のタプルと、実行に使用するシミュレーターである追加の最初の引数によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-153">The arguments to this method are given by the flattened argument tuple of the operation itself, plus an additional first argument which is the simulator to execute with.</span></span> <span data-ttu-id="c8aff-154">`(a: String, (b: Double, c: Double))` 型の名前付きタプルを想定している操作に対応するフラット化された型は `(String a, Double b, Double c)` です。</span><span class="sxs-lookup"><span data-stu-id="c8aff-154">For an operation that expects the named tuple of type `(a: String, (b: Double, c: Double))` its flattened counterpart is of type `(String a, Double b, Double c)`.</span></span>


<span data-ttu-id="c8aff-155">`Run` メソッドに引数を渡す際は、いくつかの細かい違いがあります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-155">There are some subtleties when passing arguments to a `Run` method:</span></span>

* <span data-ttu-id="c8aff-156">配列は、`Microsoft.Quantum.Simulation.Core.QArray<T>` オブジェクトにラップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-156">Arrays must be wrapped in a `Microsoft.Quantum.Simulation.Core.QArray<T>` object.</span></span>
    <span data-ttu-id="c8aff-157">`QArray` クラスには、適切なオブジェクトの順序が付けられたコレクション (`IEnumerable<T>`) を受け取ることができるコンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-157">A `QArray` class has a constructor that can take any ordered collection (`IEnumerable<T>`) of appropriate objects.</span></span>
* <span data-ttu-id="c8aff-158">Q# で `()` と示される空のタプルは、C# では `QVoid.Instance` で表されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-158">The empty tuple, `()` in Q#, is represented by `QVoid.Instance` in C#.</span></span>
* <span data-ttu-id="c8aff-159">空でないタプルは、.NET `ValueType` インスタンスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-159">Non-empty tuples are represented as .NET `ValueType` instances.</span></span>
* <span data-ttu-id="c8aff-160">Q# ユーザー定義型は、基本データ型として渡されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-160">Q# user-defined types are passed as their base type.</span></span>
* <span data-ttu-id="c8aff-161">`Run` メソッドに操作または関数を渡すには、シミュレーターの `Get<>` メソッドを使用して、操作または関数のクラスのインスタンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-161">To pass an operation or a function to a `Run` method, you have to obtain an   instance of the operation's or function's class, using the simulator's `Get<>` method.</span></span>

### <a name="processing-the-results"></a><span data-ttu-id="c8aff-162">結果を処理する</span><span class="sxs-lookup"><span data-stu-id="c8aff-162">Processing the Results</span></span>

<span data-ttu-id="c8aff-163">量子アルゴリズムの結果は、`Run` メソッドから返されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-163">The results of the quantum algorithm are returned from the `Run` method.</span></span>
<span data-ttu-id="c8aff-164">`Run` メソッドは非同期的に実行されるため、<xref:System.Threading.Tasks.Task`1> のインスタンスが返されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-164">The `Run` method executes asynchronously thus it returns an instance of <xref:System.Threading.Tasks.Task`1>.</span></span>
<span data-ttu-id="c8aff-165">実際の操作の結果を取得するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-165">There are multiple ways to get the actual operation's results.</span></span> <span data-ttu-id="c8aff-166">最も簡単な方法は、`Task` の[`Result`プロパティ](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result)を使用することです。</span><span class="sxs-lookup"><span data-stu-id="c8aff-166">The simplest is by using the `Task`'s [`Result` property](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task-1.result):</span></span>

```csharp
    var res = BellTest.Run(sim, 1000, initial).Result;
```
<span data-ttu-id="c8aff-167">[`Wait` メソッド](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait)または C#[`await` キーワード](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)などを使用する他の手法も機能します。</span><span class="sxs-lookup"><span data-stu-id="c8aff-167">but other techniques, like using the [`Wait` method](https://docs.microsoft.com/dotnet/api/system.threading.tasks.task.wait) or C# [`await` keyword](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await) will also work.</span></span>

<span data-ttu-id="c8aff-168">引数と同様に、Q# のタプルは `ValueTuple` インスタンスとして表され、Q# の配列は `QArray` インスタンスとして表されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-168">As with arguments, Q# tuples are represented as `ValueTuple` instances and Q# arrays are represented as `QArray` instances.</span></span>
<span data-ttu-id="c8aff-169">ユーザー定義型は、基本データ型として返されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-169">User-defined types are returned as their base types.</span></span>
<span data-ttu-id="c8aff-170">空のタプル (`()`) は、`QVoid` クラスのインスタンスとして返されます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-170">The empty tuple, `()`, is returned as an instance of the `QVoid` class.</span></span>

<span data-ttu-id="c8aff-171">多くの量子アルゴリズムでは、有用な回答を得るためにかなりの後処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="c8aff-171">Many quantum algorithms require substantial post-processing to derive useful answers.</span></span>
<span data-ttu-id="c8aff-172">たとえば、Shor のアルゴリズムの量子部分は、数値の要因を検出する計算の始まりにすぎません。</span><span class="sxs-lookup"><span data-stu-id="c8aff-172">For instance, the quantum part of Shor's algorithm is just the beginning of a computation that finds the factors of a number.</span></span>

<span data-ttu-id="c8aff-173">ほとんどの場合、このような後処理は従来型のドライバーで実行するのが最も単純かつ簡単です。</span><span class="sxs-lookup"><span data-stu-id="c8aff-173">In most cases, it is simplest and easiest to do this sort of post-processing in the classical driver.</span></span>
<span data-ttu-id="c8aff-174">ユーザーに結果を報告し、ディスクに書き込むことができるのは、従来型のドライバーだけです。</span><span class="sxs-lookup"><span data-stu-id="c8aff-174">Only the classical driver can report results to the user or write them to disk.</span></span>
<span data-ttu-id="c8aff-175">従来型のドライバーは、Q# で公開されていない分析ライブラリやその他の数学関数にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-175">The classical driver will have access to analytical libraries and other mathematical functions that are not exposed in Q#.</span></span>


## <a name="failures"></a><span data-ttu-id="c8aff-176">エラー</span><span class="sxs-lookup"><span data-stu-id="c8aff-176">Failures</span></span>

<span data-ttu-id="c8aff-177">操作の実行中に Q# `fail` ステートメントに到達すると、`ExecutionFailException` がスローされます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-177">When the Q# `fail` statement is reached during the execution of an operation, an `ExecutionFailException` is thrown.</span></span>

<span data-ttu-id="c8aff-178">`Run` メソッドでは `System.Task` が使用されているため、`fail` ステートメントの結果としてスローされる例外は `System.AggregateException` にラップされます。</span><span class="sxs-lookup"><span data-stu-id="c8aff-178">Due to the use of `System.Task` in the `Run` method, the exception thrown as a result of a `fail` statement will be wrapped into a `System.AggregateException`.</span></span>
<span data-ttu-id="c8aff-179">エラーを引き起こした実際の原因を調べるには、次のように `AggregateException` 
`InnerExceptions` に繰り返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8aff-179">To find the actual reason for the failure, you need to iterate into the `AggregateException` 
`InnerExceptions`, for example:</span></span>

```csharp

            try
            {
                using(var sim = new QuantumSimulator())
                {
                    /// call your operations here...
                }
            }
            catch (AggregateException e)
            {
                // Unwrap AggregateException to get the message from Q# fail statement.
                // Go through all inner exceptions.
                foreach (Exception inner in e.InnerExceptions)
                {
                    // If the exception of type ExecutionFailException
                    if (inner is ExecutionFailException failException)
                    {
                        // Print the message it contains
                        Console.WriteLine($" {failException.Message}");
                    }
                }
            }
```

## <a name="other-classical-languages"></a><span data-ttu-id="c8aff-180">その他の古典的な言語</span><span class="sxs-lookup"><span data-stu-id="c8aff-180">Other Classical Languages</span></span>

<span data-ttu-id="c8aff-181">提供されているサンプルは C#、F#、Python で書かれていますが、Quantum Development Kit では、他の言語による従来型のホスト プログラムの作成もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c8aff-181">While the samples we have provided are in C#, F#, and Python, the Quantum Development Kit also supports writing classical host programs in other languages.</span></span>
<span data-ttu-id="c8aff-182">たとえば、Visual Basic でホスト プログラムを作成する場合も[問題なく行うことができます](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net)。</span><span class="sxs-lookup"><span data-stu-id="c8aff-182">For example, if you want to write a host program in Visual Basic, [it should work just fine](https://github.com/tcNickolas/MiscQSharp/blob/master/Quantum_VBNet/README.md#using-q-with-visual-basic-net).</span></span>
