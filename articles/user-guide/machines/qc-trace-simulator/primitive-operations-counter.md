---
title: プリミティブ操作カウンター
description: Microsoft QDK プリミティブ操作カウンターについて説明します。このカウンターは、クォンタムプログラムでの操作によって使用されるプリミティブ実行の数を追跡します。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275559"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="539c4-103">プリミティブ操作カウンター</span><span class="sxs-lookup"><span data-stu-id="539c4-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="539c4-104">は、 `Primitive Operations Counter` quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="539c4-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="539c4-105">クォンタムプログラムで呼び出されたすべての操作で使用されるプリミティブ実行の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="539c4-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="539c4-106">からのすべての操作 `Microsoft.Quantum.Intrinsic` は、単一の qubit 回転、T ゲート、単一の Qubit Clifford ゲート、CNOT ゲート、およびマルチ Qubit pobservable li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="539c4-106">All operations from `Microsoft.Quantum.Intrinsic` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="539c4-107">収集された統計情報は、操作呼び出しグラフの端に集計されます。</span><span class="sxs-lookup"><span data-stu-id="539c4-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="539c4-108">ここで `T` 、操作を実装するために必要なゲートの数をカウント `CCNOT` します。</span><span class="sxs-lookup"><span data-stu-id="539c4-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="539c4-109">C# プログラム内でのプリミティブ操作カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="539c4-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="539c4-110">`CCNOT`実際に7ゲートが必要で、8ゲートを実行することを確認するに `T` `ApplySampleWithCCNOT` `T` は、次の C# コードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="539c4-110">To check that `CCNOT` indeed requires 7 `T` gates and that `ApplySampleWithCCNOT` executes 8 `T` gates we can use the following C# code:</span></span>

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

<span data-ttu-id="539c4-111">プログラムの最初の部分が実行さ `ApplySampleWithCCNOT` れます。</span><span class="sxs-lookup"><span data-stu-id="539c4-111">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="539c4-112">2番目の部分では、メソッドを使用し `QCTraceSimulator.GetMetric` て、によって実行される T ゲートの数を取得し `ApplySampleWithCCNOT` ます。</span><span class="sxs-lookup"><span data-stu-id="539c4-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="539c4-113">`GetMetric`2 つの型パラメーターを指定してを呼び出すと、特定の呼び出し先に関連付けられているメトリックの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="539c4-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="539c4-114">この例で `Primitive.CCNOT` は、操作は内で呼び出される `ApplySampleWithCCNOT` ため、呼び出しグラフにはエッジが含まれ `<Primitive.CCNOT, ApplySampleWithCCNOT>` ます。</span><span class="sxs-lookup"><span data-stu-id="539c4-114">In our example operation `Primitive.CCNOT` is called within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="539c4-115">使用されるゲートの数を取得するに `CNOT` は、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="539c4-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="539c4-116">最後に、ゲートカウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="539c4-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="539c4-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="539c4-117">See also</span></span> ##

- <span data-ttu-id="539c4-118">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="539c4-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
