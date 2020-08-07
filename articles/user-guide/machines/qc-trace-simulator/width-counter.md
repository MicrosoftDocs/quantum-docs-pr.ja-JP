---
title: 幅カウンター-Quantum 開発キット
description: クォンタムトレースシミュレーターを使用して、プログラム内の操作によって割り当てられた qubits の数をカウントする Microsoft QDK width カウンターについて説明し Q# ます。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 02f4937aaccf7bf49d6450355c6b42b273071b2e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868204"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="5d89b-103">クォンタムトレースシミュレーター: width カウンター</span><span class="sxs-lookup"><span data-stu-id="5d89b-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="5d89b-104">Width カウンターは、Quantum Development Kit[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="5d89b-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="5d89b-105">これを使用すると、プログラムの各操作によって割り当てられた qubits の数をカウントでき Q# ます。</span><span class="sxs-lookup"><span data-stu-id="5d89b-105">You can use it to count the number of qubits allocated and borrowed by each operation in a Q# program.</span></span> <span data-ttu-id="5d89b-106">プリミティブ操作によっては、追加の qubits を割り当てることができます。たとえば、制御された操作や制御される演算を乗算でき `X` `T` ます。</span><span class="sxs-lookup"><span data-stu-id="5d89b-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="5d89b-107">Width カウンターを呼び出しています</span><span class="sxs-lookup"><span data-stu-id="5d89b-107">Invoking the width counter</span></span>

<span data-ttu-id="5d89b-108">Width カウンターでクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、プロパティを true に設定した後、を `UseWidthCounter` パラメーターとして使用して**true**新しいインスタンスを作成する必要があり <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="5d89b-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="5d89b-109">C# ホストプログラムでの width カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="5d89b-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="5d89b-110">このセクションで後述する C# の例では、 <xref:microsoft.quantum.intrinsic.x> 次のサンプルコードに基づいて、乗算制御演算の実装によって割り当てられた追加の qubits の数を計算し Q# ます。</span><span class="sxs-lookup"><span data-stu-id="5d89b-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:microsoft.quantum.intrinsic.x> operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="5d89b-111">多重制御演算は、 <xref:microsoft.quantum.intrinsic.x> 合計5つの qubits に対して作用し、2つの[補助 qubits](xref:microsoft.quantum.glossary#ancilla)を割り当てます。入力幅は**5**です。</span><span class="sxs-lookup"><span data-stu-id="5d89b-111">The multiply controlled <xref:microsoft.quantum.intrinsic.x> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5**.</span></span> <span data-ttu-id="5d89b-112">カウントを確認するには、次の C# プログラムを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d89b-112">Use the following C# program to verify the counts:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
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

<span data-ttu-id="5d89b-113">プログラムの最初の部分で操作が実行され `ApplyMultiControlledX` ます。</span><span class="sxs-lookup"><span data-stu-id="5d89b-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="5d89b-114">2番目の部分では、メソッドを使用して、 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 割り当てられた qubits の数と、 `Controlled X` 操作が入力として受け取った qubits の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d89b-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="5d89b-115">最後に、次を使用して、width カウンターによって収集されたすべての統計を CSV 形式で出力できます。</span><span class="sxs-lookup"><span data-stu-id="5d89b-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="5d89b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="5d89b-116">See also</span></span>

- <span data-ttu-id="5d89b-117">Quantum Development Kit[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="5d89b-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="5d89b-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="5d89b-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="5d89b-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="5d89b-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="5d89b-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="5d89b-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
