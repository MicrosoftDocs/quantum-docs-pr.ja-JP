---
title: 幅カウンター
description: クォンタムプログラムの各操作によって割り当てられた qubits の数をカウントする Microsoft QDK Width カウンターについて説明します。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275560"
---
# <a name="width-counter"></a><span data-ttu-id="4a145-103">幅カウンター</span><span class="sxs-lookup"><span data-stu-id="4a145-103">Width Counter</span></span>

<span data-ttu-id="4a145-104">は、 `Width Counter` 各操作によって割り当てられて借用される qubits の数をカウントします。</span><span class="sxs-lookup"><span data-stu-id="4a145-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="4a145-105">名前空間のすべて `Microsoft.Quantum.Intrinsic` の操作は、単一の qubit 回転、T ゲート、単一の Qubit Clifford ゲート、CNOT ゲート、およびマルチ Qubit pobservable li の測定値で表現されます。</span><span class="sxs-lookup"><span data-stu-id="4a145-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="4a145-106">一部のプリミティブ操作では、追加の qubits を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="4a145-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="4a145-107">たとえば、制御 `X` ゲートまたは制御さ `T` れたゲートを乗算します。</span><span class="sxs-lookup"><span data-stu-id="4a145-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="4a145-108">次に、乗算制御ゲートの実装によって割り当てられた追加の qubits の数を計算してみましょう `X` 。</span><span class="sxs-lookup"><span data-stu-id="4a145-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="4a145-109">C# プログラム内での Width カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="4a145-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="4a145-110">`X`合計5つの qubits に対して制御される演算を乗算すると、2つの補助 qubits が割り当てられ、その入力幅は5になります。</span><span class="sxs-lookup"><span data-stu-id="4a145-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="4a145-111">このことを確認するには、次の C# プログラムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4a145-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="4a145-112">プログラムの最初の部分が実行さ `ApplyMultiControlledX` れます。</span><span class="sxs-lookup"><span data-stu-id="4a145-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="4a145-113">2番目の部分では、メソッドを使用して、 `QCTraceSimulator.GetMetric` 割り当てられた qubits と、 `X` 入力として受信された qubits の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="4a145-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="4a145-114">最後に、width カウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4a145-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="4a145-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a145-115">See also</span></span> ##

- <span data-ttu-id="4a145-116">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="4a145-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
