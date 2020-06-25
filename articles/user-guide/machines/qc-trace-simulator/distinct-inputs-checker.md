---
title: Distinct 入力チェッカー
description: 'Microsoft QDK の入力チェッカーについて説明します。このチェッカーは、Q # コードで共有 qubits との競合の可能性を確認します。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275623"
---
# <a name="distinct-inputs-checker"></a><span data-ttu-id="bcac7-103">Distinct 入力チェッカー</span><span class="sxs-lookup"><span data-stu-id="bcac7-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="bcac7-104">は、 `Distinct Inputs Checker` quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="bcac7-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="bcac7-105">これは、コード内の潜在的なバグを検出するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="bcac7-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="bcac7-106">このパッケージによって検出された問題を示すために、次の Q # コードを検討してください。</span><span class="sxs-lookup"><span data-stu-id="bcac7-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="bcac7-107">ユーザーは、このプログラムを参照するときに、とが呼び出される順序が関係していないことを前提として `op1` `op2` い `q1` ます。これは、とは異なる qubits `q2` と操作が異なる qubits commute で動作するためです。</span><span class="sxs-lookup"><span data-stu-id="bcac7-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="bcac7-108">ここで、この操作が使用される例を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="bcac7-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="bcac7-109">これで `op1` 、と `op2` は両方とも部分アプリケーションを使用して取得され、qubit を共有します。</span><span class="sxs-lookup"><span data-stu-id="bcac7-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="bcac7-110">上の例でユーザーがを呼び出すと、 `ApplyBoth` 操作の結果はとの順序に依存し `op1` `op2` `ApplyBoth` ます。</span><span class="sxs-lookup"><span data-stu-id="bcac7-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="bcac7-111">これは、ユーザーが期待するものではありません。</span><span class="sxs-lookup"><span data-stu-id="bcac7-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="bcac7-112">は、有効になっている `Distinct Inputs Checker` 場合にこのような状況を検出し、をスロー `DistinctInputsCheckerException` します。</span><span class="sxs-lookup"><span data-stu-id="bcac7-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="bcac7-113">詳細については、 [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)の API ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcac7-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="bcac7-114">C# プログラムでの Distinct 入力チェッカーの使用</span><span class="sxs-lookup"><span data-stu-id="bcac7-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="bcac7-115">次に、が有効なを使用して、クォンタムコンピューターのトレースシミュレーターを使用するための C# ドライバーコードの例を示し `Distinct Inputs Checker` ます。</span><span class="sxs-lookup"><span data-stu-id="bcac7-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="bcac7-116">クラスは、 `QCTraceSimulatorConfiguration` クォンタムコンピューターのトレースシミュレーターの構成を格納します。このクラスは、コンストラクターの引数として指定でき `QCTraceSimulator` ます。</span><span class="sxs-lookup"><span data-stu-id="bcac7-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="bcac7-117">を `useDistinctInputsChecker` true に設定すると `Distinct Inputs Checker` 、が有効になります。</span><span class="sxs-lookup"><span data-stu-id="bcac7-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="bcac7-118">詳細については、 [Qctracesimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)および[Qctracesimulatorconfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)に関する API ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcac7-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="bcac7-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcac7-119">See also</span></span>

- <span data-ttu-id="bcac7-120">クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="bcac7-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
