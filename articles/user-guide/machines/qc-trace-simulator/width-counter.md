---
title: 幅カウンター-Quantum 開発キット
description: 'クォンタムトレースシミュレーターを使用して、プログラム内の操作によって割り当てられた qubits の数をカウントする Microsoft QDK width カウンターについて説明し :::no-loc(Q#)::: ます。'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: e54e92cc4a76ce9f9c5aead84f2b64320d6b4f1c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691126"
---
# <a name="quantum-trace-simulator-width-counter"></a><span data-ttu-id="c2c26-103">クォンタムトレースシミュレーター: width カウンター</span><span class="sxs-lookup"><span data-stu-id="c2c26-103">Quantum trace simulator: width counter</span></span>

<span data-ttu-id="c2c26-104">Width カウンターは、Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="c2c26-104">The width counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="c2c26-105">これを使用すると、プログラムの各操作によって割り当てられた qubits の数をカウントでき :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="c2c26-105">You can use it to count the number of qubits allocated and borrowed by each operation in a :::no-loc(Q#)::: program.</span></span> <span data-ttu-id="c2c26-106">プリミティブ操作によっては、追加の qubits を割り当てることができます。たとえば、制御された操作や制御される演算を乗算でき `X` `T` ます。</span><span class="sxs-lookup"><span data-stu-id="c2c26-106">Some primitive operations can allocate extra qubits, for example, multiply controlled `X` operations or controlled `T` operations.</span></span>

## <a name="invoking-the-width-counter"></a><span data-ttu-id="c2c26-107">Width カウンターを呼び出しています</span><span class="sxs-lookup"><span data-stu-id="c2c26-107">Invoking the width counter</span></span>

<span data-ttu-id="c2c26-108">Width カウンターでクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、プロパティを true に設定した後、を `UseWidthCounter` パラメーターとして使用して **true** 新しいインスタンスを作成する必要があり <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="c2c26-108">To run the quantum trace simulator with the width counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseWidthCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a><span data-ttu-id="c2c26-109">C# ホストプログラムでの width カウンターの使用</span><span class="sxs-lookup"><span data-stu-id="c2c26-109">Using the width counter in a C# host program</span></span>

<span data-ttu-id="c2c26-110">このセクションで後述する C# の例では、 <xref:Microsoft.Quantum.Intrinsic.X> 次のサンプルコードに基づいて、乗算制御演算の実装によって割り当てられた追加の qubits の数を計算し :::no-loc(Q#)::: ます。</span><span class="sxs-lookup"><span data-stu-id="c2c26-110">The C# example that follows in this section computes the number of extra qubits allocated by the implementation of a multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

<span data-ttu-id="c2c26-111">多重制御演算は、 <xref:Microsoft.Quantum.Intrinsic.X> 合計5つの qubits に対して作用し、2つの [補助 qubits](xref:microsoft.quantum.glossary#ancilla)を割り当てます。入力幅は **5** です。</span><span class="sxs-lookup"><span data-stu-id="c2c26-111">The multiply controlled <xref:Microsoft.Quantum.Intrinsic.X> operation acts on a total of five qubits, allocates two [ancillary qubits](xref:microsoft.quantum.glossary#ancilla), and has an input width of **5** .</span></span> <span data-ttu-id="c2c26-112">カウントを確認するには、次の C# プログラムを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2c26-112">Use the following C# program to verify the counts:</span></span>

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

<span data-ttu-id="c2c26-113">プログラムの最初の部分で操作が実行され `ApplyMultiControlledX` ます。</span><span class="sxs-lookup"><span data-stu-id="c2c26-113">The first part of the program runs the `ApplyMultiControlledX` operation.</span></span> <span data-ttu-id="c2c26-114">2番目の部分では、メソッドを使用して、 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 割り当てられた qubits の数と、 `Controlled X` 操作が入力として受け取った qubits の数を取得します。</span><span class="sxs-lookup"><span data-stu-id="c2c26-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of allocated qubits as well as the number of qubits that the `Controlled X` operation received as input.</span></span> 

<span data-ttu-id="c2c26-115">最後に、次を使用して、width カウンターによって収集されたすべての統計を CSV 形式で出力できます。</span><span class="sxs-lookup"><span data-stu-id="c2c26-115">Finally, you can output all the statistics collected by the width counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="c2c26-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c2c26-116">See also</span></span>

- <span data-ttu-id="c2c26-117">Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) の概要。</span><span class="sxs-lookup"><span data-stu-id="c2c26-117">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="c2c26-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="c2c26-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="c2c26-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="c2c26-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="c2c26-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="c2c26-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter> API reference.</span></span>
