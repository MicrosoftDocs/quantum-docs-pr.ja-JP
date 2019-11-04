---
title: Width カウンタ |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442412"
---
# <a name="width-counter"></a><span data-ttu-id="f67cd-103">幅カウンター</span><span class="sxs-lookup"><span data-stu-id="f67cd-103">Width Counter</span></span>

<span data-ttu-id="f67cd-104">`Width Counter` は、各操作によって割り当てられて借用される qubits の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="f67cd-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="f67cd-105">`Microsoft.Quantum.Primitive` 名前空間のすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="f67cd-105">All operations from the `Microsoft.Quantum.Primitive` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="f67cd-106">一部のプリミティブ操作では、追加の qubits を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="f67cd-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="f67cd-107">たとえば、制御された `X` ゲートまたは制御された `T` ゲートを乗算します。</span><span class="sxs-lookup"><span data-stu-id="f67cd-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="f67cd-108">制御された複数の `X` ゲートの実装によって割り当てられた追加の qubits を計算してみましょう。</span><span class="sxs-lookup"><span data-stu-id="f67cd-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="f67cd-109">C#プログラム内での Width カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="f67cd-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="f67cd-110">合計5つの qubits に対して作用する制御 `X` の乗算では、2つの補助 qubits が割り当てられ、その入力幅は5になります。</span><span class="sxs-lookup"><span data-stu-id="f67cd-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="f67cd-111">このことを確認するには、次C#のプログラムを使用します。</span><span class="sxs-lookup"><span data-stu-id="f67cd-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="f67cd-112">プログラムの最初の部分は `MultiControlledXDriver`を実行します。</span><span class="sxs-lookup"><span data-stu-id="f67cd-112">The first part of the program executes `MultiControlledXDriver`.</span></span> <span data-ttu-id="f67cd-113">2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、割り当てられた qubits の数と、制御 `X` が入力として受け取った qubits の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f67cd-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="f67cd-114">最後に、width カウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f67cd-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="f67cd-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f67cd-115">See also</span></span> ##

- <span data-ttu-id="f67cd-116">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="f67cd-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
