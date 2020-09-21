---
title: 無効になった qubits の使用チェッカー-Quantum Development Kit
description: Microsoft QDK で無効になっている qubits 使用チェッカーについて説明します。これは、Quantum トレースシミュレーターを使用して、 Q# 無効な qubits のコードを確認します。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 18371b3798d0eaa12d4e7107f58f44379594619f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835997"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>クォンタムトレースシミュレーター: 無効になった qubits 使用チェッカー

無効化された qubits の使用チェッカーは、Quantum Development Kit の [quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。 これを使用すると、無効な qubits によって発生するコード内の潜在的なバグを検出できます。 

## <a name="invalid-qubits"></a>無効な qubits

Q#無効化された qubits use checker によって検出された問題を示すために、次のコードについて考えてみましょう。

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

に操作を適用すると `H` `q[0]` 、既に解放されている qubit が参照されるため、未定義の動作が発生する可能性があります。 無効化された Qubits Use Checker が有効になっている場合、 `InvalidatedQubitsUseCheckerException` プログラムが既に解放された qubits に操作を適用すると、例外がスローされます。 詳細については、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> を参照してください。

## <a name="invoking-the-invalidated-qubits-use-checker"></a>無効化された qubits を使用したチェッカーの呼び出し

無効化された qubits use checker でクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、 `UseInvalidatedQubitsUseChecker` プロパティを **true**に設定してから、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> パラメーターとしてを使用して新しいインスタンスを作成する必要があり `QCTraceSimulatorConfiguration` ます。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>無効化された qubits を使用した C# ホストプログラムでのチェッカーの使用

次に、無効になった qubits use checker が有効になっているクォンタムトレースシミュレーターを使用する C# ホストプログラムの例を示します。 

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

## <a name="see-also"></a>関連項目

- Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) の概要。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API リファレンス。