---
title: リソース数の取得 |Microsoft Docs
description: リソース数のドキュメントを取得する
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: f9311c1987ced4336c4e98bdb984fbee009e9acc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442467"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="26b9d-103">リソース数の取得</span><span class="sxs-lookup"><span data-stu-id="26b9d-103">Obtaining resource counts</span></span>

<span data-ttu-id="26b9d-104">従来のコンピューターで $n $ qubits をシミュレートするコストは、$n $ を使用して指数関数的に拡大できます。</span><span class="sxs-lookup"><span data-stu-id="26b9d-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="26b9d-105">これにより、完全な状態シミュレーターで実行できる量子化学シミュレーションのサイズが大幅に制限されます。</span><span class="sxs-lookup"><span data-stu-id="26b9d-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="26b9d-106">しかし、大規模な化学インスタンスの場合は、役に立つ情報が得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="26b9d-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="26b9d-107">ここでは、[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)を使用して、化学をシミュレートするための T ゲートや cnot ゲートの数などのリソースコストを自動で取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="26b9d-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="26b9d-108">このような情報は、quantum のコンピューターがこれらの quantum の化学アルゴリズムを実行するのに十分な大きさであることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="26b9d-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="26b9d-109">参考のために、提供されている `GetGateCount` サンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="26b9d-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="26b9d-110">たとえば、「[ファイルからの読み込み](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)」の例で説明したように、Broombridge スキーマから読み込まれた `FermionHamiltonian` インスタンスが既に存在するとします。</span><span class="sxs-lookup"><span data-stu-id="26b9d-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="26b9d-111">リソースの推定値を取得するための構文は、完全な状態シミュレーターでアルゴリズムを実行することとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="26b9d-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="26b9d-112">別のターゲットコンピューターを選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="26b9d-112">We simply choose a different target machine.</span></span> <span data-ttu-id="26b9d-113">リソースの推定のために、1つの Trotter ステップのコスト、または Qubitization 手法によって作成されたクォンタムウォークを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="26b9d-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="26b9d-114">これらのアルゴリズムを呼び出すための定型句は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="26b9d-114">The boilerplate for invoking these algorithms is as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="26b9d-115">ここで、トレースシミュレーターを構成して、関心のあるリソースを追跡します。</span><span class="sxs-lookup"><span data-stu-id="26b9d-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="26b9d-116">この例では、`usePrimitiveOperationsCounter` フラグを `true`に設定することによって、プリミティブなクォンタム操作をカウントします。</span><span class="sxs-lookup"><span data-stu-id="26b9d-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="26b9d-117">技術的な詳細 `throwOnUnconstraintMeasurement` は `false` に設定されています。これは、Q # コードによって測定結果の確率が正しくアサートされない場合に発生する例外を回避するためです。</span><span class="sxs-lookup"><span data-stu-id="26b9d-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="26b9d-118">次のように、ドライバープログラムからクォンタムアルゴリズムを実行します。</span><span class="sxs-lookup"><span data-stu-id="26b9d-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```