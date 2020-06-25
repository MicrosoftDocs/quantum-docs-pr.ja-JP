---
title: 無効な量子ビット使用チェッカー
description: 'Microsoft QDK で無効になっている Qubits 使用チェッカーについて説明します。これにより、Q # コードに無効な qubits があるかどうかがチェックされます。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275575"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="aaf44-103">無効になった Qubits 使用チェッカー</span><span class="sxs-lookup"><span data-stu-id="aaf44-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="aaf44-104">は、 `Invalidated Qubits Use Checker` コード内の潜在的なバグを検出するように設計された quantum コンピューター [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="aaf44-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="aaf44-105">によって検出された問題を示すために、次の Q # コードを考えてみましょう `Invalidated Qubits Use Checker` 。</span><span class="sxs-lookup"><span data-stu-id="aaf44-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="aaf44-106">`H`がに適用されている場合は、 `q[0]` 既に解放されている qubit を指します。</span><span class="sxs-lookup"><span data-stu-id="aaf44-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="aaf44-107">これにより、未定義の動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aaf44-107">This can cause undefined behavior.</span></span> <span data-ttu-id="aaf44-108">`Invalidated Qubits Use Checker`が有効な場合、 `InvalidatedQubitsUseCheckerException` 既に解放された qubit に操作が適用されると、例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="aaf44-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="aaf44-109">詳細については、 [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)の API ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaf44-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="aaf44-110">無効化された Qubits を使用した C# プログラムでのチェッカーの使用</span><span class="sxs-lookup"><span data-stu-id="aaf44-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="aaf44-111">次に、が有効になっているクォンタムコンピューターを使用するための C# ドライバーコードの例を示し `Trace
Simulator` `Invalidated Qubits Use Checker` ます。</span><span class="sxs-lookup"><span data-stu-id="aaf44-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="aaf44-112">クラスは、 `QCTraceSimulatorConfiguration` クォンタムコンピューターのトレースシミュレーターの構成を格納します。このクラスは、コンストラクターの引数として指定でき `QCTraceSimulator` ます。</span><span class="sxs-lookup"><span data-stu-id="aaf44-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="aaf44-113">を `useInvalidatedQubitsUseChecker` true に設定すると `Invalidated Qubits Use Checker` 、が有効になります。</span><span class="sxs-lookup"><span data-stu-id="aaf44-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="aaf44-114">詳細については、 [Qctracesimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)および[Qctracesimulatorconfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)に関する API ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaf44-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaf44-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="aaf44-115">See also</span></span> ##

- <span data-ttu-id="aaf44-116">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="aaf44-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
