---
title: 幅カウンター-Quantum 開発キット
description: 'Microsoft QDK width カウンターについて説明します。これは、クォンタムトレースシミュレーターを使用して、Q # プログラムの操作によって割り当てられた qubits の数をカウントします。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: af8609dc5c05f7a19b8d21755281427feb29b84c
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871521"
---
# <a name="quantum-trace-simulator-width-counter"></a>クォンタムトレースシミュレーター: width カウンター

Width カウンターは、Quantum Development Kit[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。 これを使用すると、Q # プログラムの各操作によって割り当てられた qubits の数をカウントできます。 プリミティブ操作によっては、追加の qubits を割り当てることができます。たとえば、制御された操作や制御される演算を乗算でき `X` `T` ます。

## <a name="invoking-the-width-counter"></a>Width カウンターを呼び出しています

Width カウンターでクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、プロパティを true に設定した後、を `UseWidthCounter` パラメーターとして使用して**true**新しいインスタンスを作成する必要があり <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` ます。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>C# ホストプログラムでの width カウンターの使用

このセクションで後述する C# の例では、 <xref:microsoft.quantum.intrinsic.x> 次の Q # サンプルコードに基づいて、乗算制御演算の実装によって割り当てられた追加の qubits の数を計算します。

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

多重制御演算は、 <xref:microsoft.quantum.intrinsic.x> 合計5つの qubits に対して作用し、2つの[補助 qubits](xref:microsoft.quantum.glossary#ancilla)を割り当てます。入力幅は**5**です。 カウントを確認するには、次の C# プログラムを使用します。

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

プログラムの最初の部分で操作が実行され `ApplyMultiControlledX` ます。 2番目の部分では、メソッドを使用して、 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 割り当てられた qubits の数と、 `Controlled X` 操作が入力として受け取った qubits の数を取得します。 

最後に、次を使用して、width カウンターによって収集されたすべての統計を CSV 形式で出力できます。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>関連項目

- Quantum Development Kit[クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API リファレンス。
