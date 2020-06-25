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
# <a name="invalidated-qubits-use-checker"></a>無効になった Qubits 使用チェッカー

は、 `Invalidated Qubits Use Checker` コード内の潜在的なバグを検出するように設計された quantum コンピューター [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。 によって検出された問題を示すために、次の Q # コードを考えてみましょう `Invalidated Qubits Use Checker` 。

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

`H`がに適用されている場合は、 `q[0]` 既に解放されている qubit を指します。 これにより、未定義の動作が発生する可能性があります。 `Invalidated Qubits Use Checker`が有効な場合、 `InvalidatedQubitsUseCheckerException` 既に解放された qubit に操作が適用されると、例外がスローされます。 詳細については、 [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)の API ドキュメントを参照してください。

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>無効化された Qubits を使用した C# プログラムでのチェッカーの使用

次に、が有効になっているクォンタムコンピューターを使用するための C# ドライバーコードの例を示し `Trace
Simulator` `Invalidated Qubits Use Checker` ます。 

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

クラスは、 `QCTraceSimulatorConfiguration` クォンタムコンピューターのトレースシミュレーターの構成を格納します。このクラスは、コンストラクターの引数として指定でき `QCTraceSimulator` ます。 を `useInvalidatedQubitsUseChecker` true に設定すると `Invalidated Qubits Use Checker` 、が有効になります。 詳細については、 [Qctracesimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)および[Qctracesimulatorconfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)に関する API ドキュメントを参照してください。

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
