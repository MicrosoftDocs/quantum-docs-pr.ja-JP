---
title: プリミティブ操作カウンター |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: クォンタムコンピューターのトレースシミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184884"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="271d7-103">プリミティブ操作カウンター</span><span class="sxs-lookup"><span data-stu-id="271d7-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="271d7-104">`Primitive Operations Counter` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="271d7-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="271d7-105">クォンタムプログラムで呼び出されたすべての操作で使用されるプリミティブ実行の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="271d7-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="271d7-106">`Microsoft.Quantum.Primitive` からのすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="271d7-106">All operations from `Microsoft.Quantum.Primitive` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="271d7-107">収集された統計情報は、操作呼び出しグラフの端に集計されます。</span><span class="sxs-lookup"><span data-stu-id="271d7-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="271d7-108">ここで、`CCNOT` 操作を実装するために必要な `T` ゲートの数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="271d7-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="271d7-109">C#プログラム内でのプリミティブ操作カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="271d7-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="271d7-110">`CCNOT` 実際に 7 `T` ゲートが必要であり、8 `T` ゲートを実行する `CCNOTDriver` であることC#を確認するには、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="271d7-110">To check that `CCNOT` indeed requires 7 `T` gates and that `CCNOTDriver` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="271d7-111">プログラムの最初の部分は `CCNOTDriver`を実行します。</span><span class="sxs-lookup"><span data-stu-id="271d7-111">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="271d7-112">2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、`CCNOTDriver`によって実行される T ゲートの数を取得します。</span><span class="sxs-lookup"><span data-stu-id="271d7-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `CCNOTDriver`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="271d7-113">2つの型パラメーターを指定して `GetMetric` を呼び出すと、特定の呼び出し先に関連付けられているメトリックの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="271d7-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="271d7-114">この例の操作では `Primitive.CCNOT` が `CCNOTDriver` 内で呼び出されるため、呼び出し先には `<Primitive.CCNOT,CCNOTDriver>`エッジが含まれます。</span><span class="sxs-lookup"><span data-stu-id="271d7-114">In our example operation `Primitive.CCNOT` is called within `CCNOTDriver` and therefore the call graph contains the edge `<Primitive.CCNOT,CCNOTDriver>`.</span></span> 

<span data-ttu-id="271d7-115">使用される `CNOT` ゲートの数を取得するには、次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="271d7-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="271d7-116">最後に、ゲートカウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="271d7-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="271d7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="271d7-117">See also</span></span> ##

- <span data-ttu-id="271d7-118">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="271d7-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
