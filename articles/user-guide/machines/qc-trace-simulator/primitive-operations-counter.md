---
title: プリミティブ操作カウンター-Quantum 開発キット
description: Microsoft QDK プリミティブ操作カウンターについて説明します。このカウンターは、クォンタムトレースシミュレーターを使用して、プログラム内の操作によって使用されるプリミティブプロセスを追跡し Q# ます。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8ee9ce25e680112e2f3c68d82ae9267c1b0fb355
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835980"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>クォンタムトレースシミュレーター: プリミティブ操作カウンター

プリミティブ操作カウンターは、Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。 クォンタムプログラムで呼び出されたすべての操作によって使用されるプリミティブプロセスの数をカウントします。 

すべて <xref:microsoft.quantum.intrinsic> の操作は、単一の qubit 回転、T 演算、単一の Qubit Clifford 操作、CNOT 操作、およびマルチ Qubit pobservable li の測定値で表現されます。 プリミティブ操作カウンターは、操作の [呼び出しグラフ](https://en.wikipedia.org/wiki/Call_graph)のすべての端に対する統計を集計して収集します。

## <a name="invoking-the-primitive-operation-counter"></a>プリミティブ操作カウンターを呼び出しています

プリミティブ操作カウンターを使用してクォンタムトレースシミュレーターを実行するには、インスタンスを作成し <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 、プロパティを true に設定した後、を `UsePrimitiveOperationsCounter` パラメーターとして使用して**true**新しいインスタンスを作成する必要があり <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> `QCTraceSimulatorConfiguration` ます。

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>C# ホストプログラムでのプリミティブ操作カウンターの使用

このセクションで後述する C# の例では、 <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.ccnot> 次のサンプルコードに基づいて、操作を実装するために必要な操作の数をカウントし Q# ます。

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

に7つの操作が必要で、8つの操作を実行することを確認するには `CCNOT` `T` `ApplySampleWithCCNOT` `T` 、次の C# コードを使用します。

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

プログラムの最初の部分が実行さ `ApplySampleWithCCNOT` れます。 2番目の部分では、メソッドを使用し [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) て、によって実行される操作の数を取得し `T` `ApplySampleWithCCNOT` ます。 

2つの型パラメーターを指定してを呼び出すと `GetMetric` 、特定の呼び出しのグラフの端に関連付けられているメトリックの値が返されます。 前の例では、プログラムは `Primitive.CCNOT` 内で操作を呼び出します `ApplySampleWithCCNOT` 。したがって、呼び出しグラフにはエッジが含まれてい `<Primitive.CCNOT, ApplySampleWithCCNOT>` ます。 

使用されている操作の数を取得するには `CNOT` 、次の行を追加します。
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最後に、次を使用して、プリミティブ操作カウンターによって収集されたすべての統計を CSV 形式で出力できます。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>関連項目

- Quantum Development Kit [クォンタムトレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro) の概要。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API リファレンス。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API リファレンス。