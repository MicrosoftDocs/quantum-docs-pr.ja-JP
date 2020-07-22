---
title: 量子トレース シミュレーター - Quantum Development Kit
description: Microsoft の量子コンピューター トレース シミュレーターを使用して、従来型のコードをデバッグし、Q# プログラムのリソース要件を見積もる方法について説明します。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: c01f01973ea08153cbfa35d87a588a4eae46f1b7
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871112"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="7bc66-103">Microsoft Quantum Development Kit (QDK) の量子トレース シミュレーター</span><span class="sxs-lookup"><span data-stu-id="7bc66-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="7bc66-104">QDK の <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> クラスでは、量子コンピューターの状態を実際にシミュレーションすることなく量子プログラムが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7bc66-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="7bc66-105">このため、量子トレース シミュレーターでは、何千もの量子ビットを使用する量子プログラムを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7bc66-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="7bc66-106">これは主に次の 2 つの目的で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7bc66-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="7bc66-107">量子プログラムの一部である、従来型のコードのデバッグ。</span><span class="sxs-lookup"><span data-stu-id="7bc66-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="7bc66-108">量子プログラムの特定のインスタンスを量子コンピューターで実行するために必要なリソースの推定。</span><span class="sxs-lookup"><span data-stu-id="7bc66-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="7bc66-109">実際、より限定されたメトリック セットを提供する[リソース推定器](xref:microsoft.quantum.machines.resources-estimator)は、トレース シミュレーターに基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="7bc66-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="7bc66-110">量子トレース シミュレーターの呼び出し</span><span class="sxs-lookup"><span data-stu-id="7bc66-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="7bc66-111">量子トレース シミュレーターを使用して、任意の Q# 操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7bc66-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="7bc66-112">他のターゲット マシンと同様に、最初に `QCTraceSimulator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。</span><span class="sxs-lookup"><span data-stu-id="7bc66-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="7bc66-113">`QuantumSimulator` クラスとは異なり、`QCTraceSimulator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7bc66-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="7bc66-114">測定結果の確率を指定する</span><span class="sxs-lookup"><span data-stu-id="7bc66-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="7bc66-115">量子トレース シミュレーターでは実際の量子状態がシミュレートされないため、操作内の測定結果の確率を計算することはできません。</span><span class="sxs-lookup"><span data-stu-id="7bc66-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="7bc66-116">したがって、操作に測定が含まれている場合は、<xref:microsoft.quantum.diagnostics> 名前空間の <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 操作を使用して、これらの確率を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7bc66-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> operation from the <xref:microsoft.quantum.diagnostics> namespace.</span></span> <span data-ttu-id="7bc66-117">次の例を使って説明します。</span><span class="sxs-lookup"><span data-stu-id="7bc66-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="7bc66-118">量子トレース シミュレーターで `AssertMeasurementProbability` が発生すると、`source` と `q` で `PauliZ` を測定した結果は、確率 **0.5** で `Zero` となることが記録されます。</span><span class="sxs-lookup"><span data-stu-id="7bc66-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="7bc66-119">その後 `M` 操作が実行されると、結果の確率の記録された値が検出され、`M` は、確率 **0.5** で `Zero` または `One` を返します。</span><span class="sxs-lookup"><span data-stu-id="7bc66-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="7bc66-120">量子状態を追跡するシミュレーターで同じコードを実行すると、シミュレーターは `AssertMeasurementProbability` で指定された確率が正しいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7bc66-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="7bc66-121">`AssertMeasurementProbability` によって注釈が付けられていない操作が少なくとも 1 つある場合は、シミュレーターによって [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception) がスローされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7bc66-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="7bc66-122">量子トレース シミュレーターのツール</span><span class="sxs-lookup"><span data-stu-id="7bc66-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="7bc66-123">QDK には、プログラム内のバグを検出し、量子プログラム リソースの見積もりを実行するために、量子トレース シミュレーターで使用できる 5 つのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7bc66-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="7bc66-124">ツール</span><span class="sxs-lookup"><span data-stu-id="7bc66-124">Tool</span></span> | <span data-ttu-id="7bc66-125">説明</span><span class="sxs-lookup"><span data-stu-id="7bc66-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="7bc66-126">個別入力チェッカー</span><span class="sxs-lookup"><span data-stu-id="7bc66-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="7bc66-127">共有量子ビットと競合する可能性があるかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="7bc66-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="7bc66-128">無効な量子ビット使用チェッカー</span><span class="sxs-lookup"><span data-stu-id="7bc66-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="7bc66-129">プログラムが既に解放されている量子ビットに操作を適用していないかどうかを確認します</span><span class="sxs-lookup"><span data-stu-id="7bc66-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="7bc66-130">プリミティブ操作カウンター</span><span class="sxs-lookup"><span data-stu-id="7bc66-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="7bc66-131">量子プログラムで呼び出されたすべての操作によって使用されるプリミティブ実行の数をカウントします</span><span class="sxs-lookup"><span data-stu-id="7bc66-131">Counts the number of primitive executions used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="7bc66-132">深さのカウンター</span><span class="sxs-lookup"><span data-stu-id="7bc66-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="7bc66-133">量子プログラムで呼び出された各操作の深さの下限を表すカウントを収集します</span><span class="sxs-lookup"><span data-stu-id="7bc66-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="7bc66-134">幅のカウンター</span><span class="sxs-lookup"><span data-stu-id="7bc66-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="7bc66-135">量子プログラムの各操作によって割り当てられ、借用された量子ビットの数をカウントします</span><span class="sxs-lookup"><span data-stu-id="7bc66-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="7bc66-136">これらの各ツールは、`QCTraceSimulatorConfiguration` で適切なフラグを設定し、構成を `QCTraceSimulator` 宣言に渡すことによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="7bc66-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="7bc66-137">これらの各ツールの使用方法の詳細については、前の一覧のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bc66-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="7bc66-138">`QCTraceSimulator` の構成の詳細については、「[QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bc66-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="7bc66-139">QCTraceSimulator のメソッド</span><span class="sxs-lookup"><span data-stu-id="7bc66-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="7bc66-140">`QCTraceSimulator` には、量子操作中に追跡されるメトリックの値を取得するための組み込みメソッドがいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="7bc66-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="7bc66-141">[QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) と [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) メソッドの例については、[プリミティブ操作カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)、[深さのカウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)、および[幅のカウンター](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bc66-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="7bc66-142">使用可能なすべてのメソッドの詳細については、Q# API リファレンスの [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bc66-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7bc66-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="7bc66-143">See also</span></span>

- [<span data-ttu-id="7bc66-144">量子リソース推定器</span><span class="sxs-lookup"><span data-stu-id="7bc66-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="7bc66-145">量子 Toffoli シミュレーター</span><span class="sxs-lookup"><span data-stu-id="7bc66-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="7bc66-146">量子完全状態シミュレーター</span><span class="sxs-lookup"><span data-stu-id="7bc66-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 