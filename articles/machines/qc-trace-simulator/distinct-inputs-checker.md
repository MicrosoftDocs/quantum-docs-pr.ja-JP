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

## <a name="see-also"></a>関連項目

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
