---
title: Distinct 入力チェッカー
description: 'Microsoft QDK の入力チェッカーについて説明します。このチェッカーは、Q # コードで共有 qubits との競合の可能性を確認します。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907105"
---
# <a name="distinct-inputs-checker"></a>Distinct 入力チェッカー

`Distinct Inputs Checker` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。 これは、コード内の潜在的なバグを検出するように設計されています。 このパッケージによって検出された問題を示すために、次の Q # コードを検討してください。

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

ユーザーは、このプログラムを参照するときに、`op1` と `op2` が呼び出される順序は関係ありません。 `q1` と `q2` は異なる qubits と操作が異なる qubits commute で動作するためです。 ここで、この操作が使用される例を考えてみましょう。

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

`op1` と `op2` は両方とも部分アプリケーションを使用して取得され、qubit を共有します。 上の例でユーザーが `ApplyBoth` を呼び出すと、操作の結果は `ApplyBoth`内の `op1` と `op2` の順序に依存します。 これは、ユーザーが期待するものではありません。 このような状況は、有効にすると `Distinct Inputs Checker` によって検出され、`DistinctInputsCheckerException`がスローされます。 詳細については、 [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)の API ドキュメントを参照してください。

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>C#プログラムでの Distinct 入力チェッカーの使用

次に、クォンタムコンピューターのC#トレースシミュレーターを使用して `Distinct Inputs Checker` を有効にした場合のドライバーコードの例を示します。

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

クラス `QCTraceSimulatorConfiguration` には、クォンタムコンピューターのトレースシミュレーターの構成が格納され、`QCTraceSimulator` コンストラクターの引数として指定できます。 `useDistinctInputsChecker` が true に設定されている場合、`Distinct Inputs Checker` が有効になります。 詳細については、 [Qctracesimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)および[Qctracesimulatorconfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)に関する API ドキュメントを参照してください。

## <a name="see-also"></a>参照

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
