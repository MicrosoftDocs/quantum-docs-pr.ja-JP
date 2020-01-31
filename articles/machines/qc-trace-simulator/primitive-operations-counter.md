---
title: プリミティブ操作カウンター |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820421"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="47b52-103">プリミティブ操作カウンター</span><span class="sxs-lookup"><span data-stu-id="47b52-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="47b52-104">`Primitive Operations Counter` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="47b52-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="47b52-105">クォンタムプログラムで呼び出されたすべての操作で使用されるプリミティブ実行の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="47b52-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="47b52-106">`Microsoft.Quantum.Intrinsic` からのすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="47b52-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="47b52-107">収集された統計情報は、操作呼び出しグラフの端に集計されます。</span><span class="sxs-lookup"><span data-stu-id="47b52-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="47b52-108">ここで、`CCNOT` 操作を実装するために必要な `T` ゲートの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="47b52-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="47b52-109">C#プログラム内でのプリミティブ操作カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="47b52-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="47b52-110">`CCNOT` 実際に 7 `T` ゲートが必要であり、8 `T` ゲートを実行する `ApplySampleWithCCNOT` であることC#を確認するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="47b52-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="47b52-111">プログラムの最初の部分は `ApplySampleWithCCNOT`を実行します。</span><span class="sxs-lookup"><span data-stu-id="47b52-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="47b52-112">2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、`ApplySampleWithCCNOT`によって実行される T ゲートの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="47b52-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="47b52-113">2つの型パラメーターを指定して `GetMetric` を呼び出すと、特定の呼び出し先に関連付けられているメトリックの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="47b52-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="47b52-114">この例の操作では `Primitive.CCNOT` が `ApplySampleWithCCNOT` 内で呼び出されるため、呼び出し先には `<Primitive.CCNOT, ApplySampleWithCCNOT>`エッジが含まれます。</span><span class="sxs-lookup"><span data-stu-id="47b52-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="47b52-115">使用される `CNOT` ゲートの数を取得するには、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="47b52-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="47b52-116">最後に、ゲートカウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="47b52-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="47b52-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="47b52-117">See also</span></span> ##

- <span data-ttu-id="47b52-118">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="47b52-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
