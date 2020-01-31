---
title: 深さカウンター |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 07f927c794e2c62e53e4e053b5bc683d24bbed8d
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820472"
---
# <a name="depth-counter"></a><span data-ttu-id="f4abf-103">深さカウンター</span><span class="sxs-lookup"><span data-stu-id="f4abf-103">Depth Counter</span></span>

<span data-ttu-id="f4abf-104">`Depth Counter` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f4abf-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="f4abf-105">これは、クォンタムプログラムで呼び出されたすべての操作の深さのカウントを収集するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f4abf-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="f4abf-106"><xref:microsoft.quantum.intrinsic> からのすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="f4abf-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="f4abf-107">ユーザーは、<xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>の [`gateTimes`] フィールドを使用して、各プリミティブ操作の深さを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f4abf-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="f4abf-108">既定では、すべての操作の深さは 0 (深度1を持つ T ゲートを除く) です。</span><span class="sxs-lookup"><span data-stu-id="f4abf-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="f4abf-109">つまり、既定では、演算の T の深さのみが計算されます (これが望ましい場合があります)。</span><span class="sxs-lookup"><span data-stu-id="f4abf-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="f4abf-110">収集された統計情報は、操作呼び出しグラフのすべての端に集計されます。</span><span class="sxs-lookup"><span data-stu-id="f4abf-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="f4abf-111">ここで、<xref:microsoft.quantum.intrinsic.ccnot> 操作の <xref:microsoft.quantum.intrinsic.t> の深さを計算してみましょう。</span><span class="sxs-lookup"><span data-stu-id="f4abf-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="f4abf-112">次の Q # サンプルコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4abf-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="f4abf-113">C#プログラム内での Depth カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="f4abf-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="f4abf-114">`CCNOT` に `T` 深度5があり、`ApplySampleWithCCNOT` に `T` 深さ6があることを確認するC#には、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f4abf-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="f4abf-115">プログラムの最初の部分は `ApplySampleWithCCNOT`を実行します。</span><span class="sxs-lookup"><span data-stu-id="f4abf-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="f4abf-116">2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、`CCNOT` と `ApplySampleWithCCNOT`の `T` の深さを取得します。</span><span class="sxs-lookup"><span data-stu-id="f4abf-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="f4abf-117">最後に、`Depth Counter` によって収集されたすべての統計を CSV 形式で出力するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f4abf-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="f4abf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4abf-118">See also</span></span> ##

- <span data-ttu-id="f4abf-119">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="f4abf-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
