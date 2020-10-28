---
title: 深さカウンター-Quantum 開発キット
description: 'クォンタムトレースシミュレーターを使用して、プログラムで呼び出されたすべての操作の深さのカウントを収集する Microsoft QDK の深さカウンターについて説明し :::no-loc(Q#)::: ます。'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 89d8a2c9f2ecd5c5332215cd4307bcf4a6422036
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692103"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="c4c69-103">クォンタムトレースシミュレーター: 深度カウンター</span><span class="sxs-lookup"><span data-stu-id="c4c69-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="c4c69-104">この深さカウンターは、Quantum Development Kit [quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="c4c69-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="c4c69-105">このツールを使用すると、クォンタムプログラムで呼び出されたすべての操作の深さの下限を表すカウントを収集できます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="c4c69-106">深さの値</span><span class="sxs-lookup"><span data-stu-id="c4c69-106">Depth values</span></span>

<span data-ttu-id="c4c69-107">既定では、すべての操作の深さは **0** `T` です。ただし、操作の深さは **1** です。</span><span class="sxs-lookup"><span data-stu-id="c4c69-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1** .</span></span> <span data-ttu-id="c4c69-108">つまり、既定では、 `T` 操作の深さのみが計算されます (通常は望ましい)。</span><span class="sxs-lookup"><span data-stu-id="c4c69-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="c4c69-109">この深さカウンターは、操作の [呼び出しグラフ](https://en.wikipedia.org/wiki/Call_graph)のすべての端に対する統計を集計して収集します。</span><span class="sxs-lookup"><span data-stu-id="c4c69-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="c4c69-110">すべて <xref:Microsoft.Quantum.Intrinsic> の操作は、単一の qubit の回転、 <xref:Microsoft.Quantum.Intrinsic.T> 操作、1つのシングル Qubit Clifford 操作、 <xref:Microsoft.Quantum.Intrinsic.CNOT> 操作、およびマルチ qubit pobservable li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-110">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, <xref:Microsoft.Quantum.Intrinsic.T> operations, single-qubit Clifford operations, <xref:Microsoft.Quantum.Intrinsic.CNOT> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="c4c69-111">ユーザーは、のフィールドを使用して、各プリミティブ操作の深さを設定でき `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> ます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="c4c69-112">深度カウンターを呼び出しています</span><span class="sxs-lookup"><span data-stu-id="c4c69-112">Invoking the depth counter</span></span>

<span data-ttu-id="c4c69-113">詳細カウンターを使用してクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、その `UseDepthCounter` プロパティを **true** に設定してから、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> パラメーターとしてを使用して新しいインスタンスを作成する必要があり `QCTraceSimulatorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="c4c69-114">C# ホストプログラムでの深度カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="c4c69-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="c4c69-115">このセクションの次の C# の例では、 `T` 次の `CCNOT` サンプルコードに基づいて、操作の深さを計算し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="c4c69-116">深度が5で深さが6であることを確認するには `CCNOT` `T` **5** `ApplySampleWithCCNOT` `T` 、次の C# コードを使用します。 **6**</span><span class="sxs-lookup"><span data-stu-id="c4c69-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6** , use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="c4c69-117">プログラムの最初の部分が実行さ `ApplySampleWithCCNOT` れます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="c4c69-118">2番目の部分では、メソッドを使用し [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) `T` て、との深さを取得し `CCNOT` `ApplySampleWithCCNOT` ます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="c4c69-119">最後に、次を使用して、深度カウンターによって収集されたすべての統計を CSV 形式で出力できます。</span><span class="sxs-lookup"><span data-stu-id="c4c69-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="c4c69-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4c69-120">See also</span></span>

- <span data-ttu-id="c4c69-121">Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) の概要。</span><span class="sxs-lookup"><span data-stu-id="c4c69-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="c4c69-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="c4c69-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="c4c69-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="c4c69-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="c4c69-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="c4c69-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
