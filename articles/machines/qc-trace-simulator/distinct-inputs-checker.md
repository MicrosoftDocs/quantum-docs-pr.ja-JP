---
title: Distinct 入力チェッカー |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820965"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="eb059-103">Distinct 入力チェッカー</span><span class="sxs-lookup"><span data-stu-id="eb059-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="eb059-104">`Distinct Inputs Checker` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb059-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="eb059-105">これは、コード内の潜在的なバグを検出するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="eb059-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="eb059-106">このパッケージによって検出された問題を示すために、次の Q # コードを検討してください。</span><span class="sxs-lookup"><span data-stu-id="eb059-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

<span data-ttu-id="eb059-107">ユーザーは、このプログラムを参照するときに、`op1` と `op2` が呼び出される順序は関係ありません。 `q1` と `q2` は異なる qubits と操作が異なる qubits commute で動作するためです。</span><span class="sxs-lookup"><span data-stu-id="eb059-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="eb059-108">ここで、この操作が使用される例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="eb059-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="eb059-109">`op1` と `op2` は両方とも部分アプリケーションを使用して取得され、qubit を共有します。</span><span class="sxs-lookup"><span data-stu-id="eb059-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="eb059-110">上の例でユーザーが `ApplyBoth` を呼び出すと、操作の結果は `ApplyBoth`内の `op1` と `op2` の順序に依存します。</span><span class="sxs-lookup"><span data-stu-id="eb059-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="eb059-111">これは、ユーザーが期待するものではありません。</span><span class="sxs-lookup"><span data-stu-id="eb059-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="eb059-112">このような状況は、有効にすると `Distinct Inputs Checker` によって検出され、`DistinctInputsCheckerException`がスローされます。</span><span class="sxs-lookup"><span data-stu-id="eb059-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="eb059-113">詳細については、 [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)の API ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb059-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="eb059-114">C#プログラムでの Distinct 入力チェッカーの使用</span><span class="sxs-lookup"><span data-stu-id="eb059-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="eb059-115">次に、クォンタムコンピューターのC#トレースシミュレーターを使用して `Distinct Inputs Checker` を有効にした場合のドライバーコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="eb059-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="eb059-116">クラス `QCTraceSimulatorConfiguration` には、クォンタムコンピューターのトレースシミュレーターの構成が格納され、`QCTraceSimulator` コンストラクターの引数として指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb059-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="eb059-117">`useDistinctInputsChecker` が true に設定されている場合、`Distinct Inputs Checker` が有効になります。</span><span class="sxs-lookup"><span data-stu-id="eb059-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="eb059-118">詳細については、 [Qctracesimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)および[Qctracesimulatorconfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)に関する API ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb059-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb059-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb059-119">See also</span></span>

- <span data-ttu-id="eb059-120">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="eb059-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
