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
# <a name="distinct-inputs-checker"></a>Distinct 入力チェッカー

は、 `Distinct Inputs Checker` quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。 これは、コード内の潜在的なバグを検出するように設計されています。 このパッケージによって検出された問題を示すために、次の Q # コードを検討してください。

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

ユーザーは、このプログラムを参照するときに、とが呼び出される順序が関係していないことを前提として `op1` `op2` い `q1` ます。これは、とは異なる qubits `q2` と操作が異なる qubits commute で動作するためです。 ここで、この操作が使用される例を考えてみましょう。

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

これで `op1` 、と `op2` は両方とも部分アプリケーションを使用して取得され、qubit を共有します。 上の例でユーザーがを呼び出すと、 `ApplyBoth` 操作の結果はとの順序に依存し `op1` `op2` `ApplyBoth` ます。 これは、ユーザーが期待するものではありません。 は、有効になっている `Distinct Inputs Checker` 場合にこのような状況を検出し、をスロー `DistinctInputsCheckerException` します。 詳細については、 [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)の API ドキュメントを参照してください。

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>C# プログラムでの Distinct 入力チェッカーの使用

次に、が有効なを使用して、クォンタムコンピューターのトレースシミュレーターを使用するための C# ドライバーコードの例を示し `Distinct Inputs Checker` ます。

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

クラスは、 `QCTraceSimulatorConfiguration` クォンタムコンピューターのトレースシミュレーターの構成を格納します。このクラスは、コンストラクターの引数として指定でき `QCTraceSimulator` ます。 を `useDistinctInputsChecker` true に設定すると `Distinct Inputs Checker` 、が有効になります。 詳細については、 [Qctracesimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)および[Qctracesimulatorconfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)に関する API ドキュメントを参照してください。

## <a name="see-also"></a>関連項目

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
