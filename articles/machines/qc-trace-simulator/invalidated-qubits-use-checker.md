---
title: 無効になった qubits use checker |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820880"
---
# <a name="invalidated-qubits-use-checker"></a>無効になった Qubits 使用チェッカー

`Invalidated Qubits Use Checker` は、コード内の潜在的なバグを検出するように設計された quantum コンピューター [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。 `Invalidated Qubits Use Checker`によって検出された問題を示すために、次の Q # コードを考えてみましょう。

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

`H` が `q[0]` に適用されると、既に解放されている qubit を指します。 これにより、未定義の動作が発生する可能性があります。 `Invalidated Qubits Use Checker` が有効になっている場合、既に解放されている qubit に操作が適用されると、例外 `InvalidatedQubitsUseCheckerException` がスローされます。 詳細については、 [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)の API ドキュメントを参照してください。

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>無効化された Qubits を使用しC#てプログラムで使用する

次に、`Invalidated Qubits Use Checker` が有効C#になっているクォンタムコンピューター `Trace
Simulator` を使用するためのドライバーコードの例を示します。 

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

クラス `QCTraceSimulatorConfiguration` には、クォンタムコンピューターのトレースシミュレーターの構成が格納され、`QCTraceSimulator` コンストラクターの引数として指定できます。 `useInvalidatedQubitsUseChecker` が true に設定されている場合、`Invalidated Qubits Use Checker` が有効になります。 詳細については、 [Qctracesimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)および[Qctracesimulatorconfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)に関する API ドキュメントを参照してください。

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
