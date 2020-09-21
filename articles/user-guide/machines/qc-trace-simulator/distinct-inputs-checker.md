---
title: Distinct 入力チェッカー-Quantum Development Kit
description: Microsoft QDK distinct 入力チェッカーについて説明します。これは、Quantum トレースシミュレーターを使用して、 Q# 共有 qubits との潜在的な競合をコードに確認します。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: bcb0bc92a546279496d27ad9b8c5f943ac133e2a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833470"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>クォンタムトレースシミュレーター: 個別入力チェッカー

Distinct 入力チェッカーは、Quantum Development Kit [quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。 これを使用すると、共有 qubits との競合によって発生する可能性のあるコード内のバグを検出できます。 

## <a name="conflicts-with-shared-qubits"></a>共有 qubits との競合

Q#Distinct 入力チェッカーによって検出された問題を示すために、次のコードについて考えてみましょう。

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

このプログラムを見ると、との呼び出し順序が異なることを想定できます `op1` `op2` `q1` 。これは、とは異なる qubits `q2` commute に作用する演算子と操作が異なるためです。 

ここで、次の例を考えてみます。

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

`op1`と `op2` は両方とも部分アプリケーションを使用して取得され、qubit を共有することに注意してください。 この例でを呼び出すと、 `ApplyBoth` 操作の結果は、 `op1` 発生すると予想される順序と内部ではなく、の順序によって決まり `op2` `ApplyBoth` ます。 Distinct 入力チェッカーを有効にすると、このような状況が検出され、がスローさ `DistinctInputsCheckerException` れます。 詳細については、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API ライブラリの「」を参照してください Q# 。

## <a name="invoking-the-distinct-inputs-checker"></a>個別入力チェッカーの呼び出し

Distinct 入力チェッカーを使用してクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、 `UseDistinctInputsChecker` プロパティを **true**に設定してから、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> パラメーターとしてを使用して新しいインスタンスを作成する必要があり `QCTraceSimulatorConfiguration` ます。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>C# ホストプログラムでの distinct 入力チェッカーの使用

次に、distinct 入力チェッカーが有効になっているクォンタムトレースシミュレーターを使用する C# ホストプログラムの例を示します。

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

## <a name="see-also"></a>関連項目

- Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) の概要。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API リファレンス。
