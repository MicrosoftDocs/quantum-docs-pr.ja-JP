---
title: 深さカウンター-Quantum 開発キット
description: クォンタムトレースシミュレーターを使用して、プログラムで呼び出されたすべての操作の深さのカウントを収集する Microsoft QDK の深さカウンターについて説明し Q# ます。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9c3a772861582e5c49fe5ad27519c25a59d617b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859042"
---
# <a name="quantum-trace-simulator-depth-counter"></a>クォンタムトレースシミュレーター: 深度カウンター

この深さカウンターは、Quantum Development Kit [quantum トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。
このツールを使用すると、クォンタムプログラムで呼び出されたすべての操作の深さの下限を表すカウントを収集できます。 

## <a name="depth-values"></a>深さの値

既定では、すべての操作の深さは **0** `T` です。ただし、操作の深さは **1** です。 つまり、既定では、 `T` 操作の深さのみが計算されます (通常は望ましい)。 この深さカウンターは、操作の [呼び出しグラフ](https://en.wikipedia.org/wiki/Call_graph)のすべての端に対する統計を集計して収集します。

すべて <xref:Microsoft.Quantum.Intrinsic> の操作は、単一の qubit の回転、 <xref:Microsoft.Quantum.Intrinsic.T> 操作、1つのシングル Qubit Clifford 操作、 <xref:Microsoft.Quantum.Intrinsic.CNOT> 操作、およびマルチ qubit pobservable li の測定値で表現されます。 ユーザーは、のフィールドを使用して、各プリミティブ操作の深さを設定でき `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> ます。

## <a name="invoking-the-depth-counter"></a>深度カウンターを呼び出しています

詳細カウンターを使用してクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、その `UseDepthCounter` プロパティを **true** に設定してから、 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> パラメーターとしてを使用して新しいインスタンスを作成する必要があり `QCTraceSimulatorConfiguration` ます。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>C# ホストプログラムでの深度カウンターの使用

このセクションの次の C# の例では、 `T` 次の `CCNOT` サンプルコードに基づいて、操作の深さを計算し Q# ます。

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

深度が5で深さが6であることを確認するには `CCNOT` `T`  `ApplySampleWithCCNOT` `T` 、次の C# コードを使用します。 

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

プログラムの最初の部分が実行さ `ApplySampleWithCCNOT` れます。 2番目の部分では、メソッドを使用し [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) `T` て、との深さを取得し `CCNOT` `ApplySampleWithCCNOT` ます。 

最後に、次を使用して、深度カウンターによって収集されたすべての統計を CSV 形式で出力できます。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>関連項目

- Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) の概要。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API リファレンス。
