---
title: プリミティブ操作カウンター-Quantum 開発キット
description: 'Microsoft QDK プリミティブ操作カウンターについて説明します。このカウンターは、クォンタムトレースシミュレーターを使用して、プログラム内の操作によって使用されるプリミティブプロセスを追跡し Q# ます。'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: bf75eb94696a489a587316928bc3f33baa4a1785
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690945"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="8e645-103">クォンタムトレースシミュレーター: プリミティブ操作カウンター</span><span class="sxs-lookup"><span data-stu-id="8e645-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="8e645-104">プリミティブ操作カウンターは、Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="8e645-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="8e645-105">クォンタムプログラムで呼び出されたすべての操作によって使用されるプリミティブプロセスの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="8e645-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="8e645-106">すべて <xref:Microsoft.Quantum.Intrinsic> の操作は、単一の qubit 回転、T 演算、単一の Qubit Clifford 操作、CNOT 操作、およびマルチ Qubit pobservable li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="8e645-106">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="8e645-107">プリミティブ操作カウンターは、操作の [呼び出しグラフ](https://en.wikipedia.org/wiki/Call_graph)のすべての端に対する統計を集計して収集します。</span><span class="sxs-lookup"><span data-stu-id="8e645-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="8e645-108">プリミティブ操作カウンターを呼び出しています</span><span class="sxs-lookup"><span data-stu-id="8e645-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="8e645-109">プリミティブ操作カウンターを使用してクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、プロパティを true に設定した後、を `UsePrimitiveOperationsCounter` パラメーターとして使用して **true** 新しいインスタンスを作成する必要があり <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="8e645-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="8e645-110">C# ホストプログラムでのプリミティブ操作カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="8e645-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="8e645-111">このセクションで後述する C# の例では、 <xref:Microsoft.Quantum.Intrinsic.T> <xref:Microsoft.Quantum.Intrinsic.ccnot> 次のサンプルコードに基づいて、操作を実装するために必要な操作の数をカウントし Q# ます。</span><span class="sxs-lookup"><span data-stu-id="8e645-111">The C# example that follows in this section counts how many <xref:Microsoft.Quantum.Intrinsic.T> operations are needed to implement the <xref:Microsoft.Quantum.Intrinsic.ccnot> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="8e645-112">に7つの操作が必要で、8つの操作を実行することを確認するには `CCNOT` `T` `ApplySampleWithCCNOT` `T` 、次の C# コードを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e645-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="8e645-113">プログラムの最初の部分が実行さ `ApplySampleWithCCNOT` れます。</span><span class="sxs-lookup"><span data-stu-id="8e645-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="8e645-114">2番目の部分では、メソッドを使用し [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) て、によって実行される操作の数を取得し `T` `ApplySampleWithCCNOT` ます。</span><span class="sxs-lookup"><span data-stu-id="8e645-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="8e645-115">2つの型パラメーターを指定してを呼び出すと `GetMetric` 、特定の呼び出しのグラフの端に関連付けられているメトリックの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="8e645-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="8e645-116">前の例では、プログラムは `Primitive.CCNOT` 内で操作を呼び出します `ApplySampleWithCCNOT` 。したがって、呼び出しグラフにはエッジが含まれてい `<Primitive.CCNOT, ApplySampleWithCCNOT>` ます。</span><span class="sxs-lookup"><span data-stu-id="8e645-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="8e645-117">使用されている操作の数を取得するには `CNOT` 、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="8e645-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="8e645-118">最後に、次を使用して、プリミティブ操作カウンターによって収集されたすべての統計を CSV 形式で出力できます。</span><span class="sxs-lookup"><span data-stu-id="8e645-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="8e645-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e645-119">See also</span></span>

- <span data-ttu-id="8e645-120">Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) の概要。</span><span class="sxs-lookup"><span data-stu-id="8e645-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="8e645-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="8e645-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="8e645-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="8e645-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="8e645-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="8e645-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>