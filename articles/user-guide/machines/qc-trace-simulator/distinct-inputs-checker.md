---
title: Distinct 入力チェッカー-Quantum Development Kit
description: 'Microsoft QDK distinct 入力チェッカーについて説明します。これは、Quantum トレースシミュレーターを使用して、共有 qubits と競合する可能性があることを Q # コードで確認します。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871146"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="eced9-103">クォンタムトレースシミュレーター: 個別入力チェッカー</span><span class="sxs-lookup"><span data-stu-id="eced9-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="eced9-104">Distinct 入力チェッカーは、Quantum Development Kit [quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。</span><span class="sxs-lookup"><span data-stu-id="eced9-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="eced9-105">これを使用すると、共有 qubits との競合によって発生する可能性のあるコード内のバグを検出できます。</span><span class="sxs-lookup"><span data-stu-id="eced9-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="eced9-106">共有 qubits との競合</span><span class="sxs-lookup"><span data-stu-id="eced9-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="eced9-107">個別の入力チェッカーによって検出された問題を示すために、次のような Q # コードを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="eced9-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="eced9-108">このプログラムを見ると、との呼び出し順序が異なることを想定できます `op1` `op2` `q1` 。これは、とは異なる qubits `q2` commute に作用する演算子と操作が異なるためです。</span><span class="sxs-lookup"><span data-stu-id="eced9-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="eced9-109">ここで、次の例を考えてみます。</span><span class="sxs-lookup"><span data-stu-id="eced9-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="eced9-110">`op1`と `op2` は両方とも部分アプリケーションを使用して取得され、qubit を共有することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="eced9-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="eced9-111">この例でを呼び出すと、 `ApplyBoth` 操作の結果は、 `op1` 発生すると予想される順序と内部ではなく、の順序によって決まり `op2` `ApplyBoth` ます。</span><span class="sxs-lookup"><span data-stu-id="eced9-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="eced9-112">Distinct 入力チェッカーを有効にすると、このような状況が検出され、がスローさ `DistinctInputsCheckerException` れます。</span><span class="sxs-lookup"><span data-stu-id="eced9-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="eced9-113">詳細については、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> Q # API ライブラリの「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eced9-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="eced9-114">個別入力チェッカーの呼び出し</span><span class="sxs-lookup"><span data-stu-id="eced9-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="eced9-115">Distinct 入力チェッカーを使用してクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、 `UseDistinctInputsChecker` プロパティを**true**に設定してから、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> パラメーターとしてを使用して新しいインスタンスを作成する必要があり `QCTraceSimulatorConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="eced9-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="eced9-116">C# ホストプログラムでの distinct 入力チェッカーの使用</span><span class="sxs-lookup"><span data-stu-id="eced9-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="eced9-117">次に、distinct 入力チェッカーが有効になっているクォンタムトレースシミュレーターを使用する C# ホストプログラムの例を示します。</span><span class="sxs-lookup"><span data-stu-id="eced9-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="eced9-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="eced9-118">See also</span></span>

- <span data-ttu-id="eced9-119">Quantum Development Kit[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。</span><span class="sxs-lookup"><span data-stu-id="eced9-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="eced9-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="eced9-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="eced9-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="eced9-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="eced9-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API リファレンス。</span><span class="sxs-lookup"><span data-stu-id="eced9-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
