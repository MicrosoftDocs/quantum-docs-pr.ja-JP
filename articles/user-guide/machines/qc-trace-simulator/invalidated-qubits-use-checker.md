---
title: 無効になった qubits の使用チェッカー-Quantum Development Kit
description: Microsoft QDK で無効になっている qubits 使用チェッカーについて説明します。これは、Quantum トレースシミュレーターを使用して、 Q# 無効な qubits のコードを確認します。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: c451747badba03801bd4ecd419420f131ac502d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868289"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="5c862-103">クォンタムトレースシミュレーター: 無効になった qubits 使用チェッカー</span><span class="sxs-lookup"><span data-stu-id="5c862-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="5c862-104">無効化された qubits の使用チェッカーは、Quantum Development Kit の[quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="5c862-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="5c862-105">これを使用すると、無効な qubits によって発生するコード内の潜在的なバグを検出できます。</span><span class="sxs-lookup"><span data-stu-id="5c862-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="5c862-106">無効な qubits</span><span class="sxs-lookup"><span data-stu-id="5c862-106">Invalid qubits</span></span>

<span data-ttu-id="5c862-107">Q#無効化された qubits use checker によって検出された問題を示すために、次のコードについて考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="5c862-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="5c862-108">に操作を適用すると `H` `q[0]` 、既に解放されている qubit が参照されるため、未定義の動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c862-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="5c862-109">無効化された Qubits Use Checker が有効になっている場合、 `InvalidatedQubitsUseCheckerException` プログラムが既に解放された qubits に操作を適用すると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="5c862-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="5c862-110">詳細については、「<xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c862-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="5c862-111">無効化された qubits を使用したチェッカーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="5c862-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="5c862-112">無効化された qubits use checker でクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、 `UseInvalidatedQubitsUseChecker` プロパティを**true**に設定してから、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> パラメーターとしてを使用して新しいインスタンスを作成する必要があり `QCTraceSimulatorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="5c862-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="5c862-113">無効化された qubits を使用した C# ホストプログラムでのチェッカーの使用</span><span class="sxs-lookup"><span data-stu-id="5c862-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="5c862-114">次に、無効になった qubits use checker が有効になっているクォンタムトレースシミュレーターを使用する C# ホストプログラムの例を示します。</span><span class="sxs-lookup"><span data-stu-id="5c862-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="5c862-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c862-115">See also</span></span>

- <span data-ttu-id="5c862-116">Quantum Development Kit[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="5c862-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="5c862-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="5c862-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="5c862-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="5c862-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="5c862-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="5c862-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>