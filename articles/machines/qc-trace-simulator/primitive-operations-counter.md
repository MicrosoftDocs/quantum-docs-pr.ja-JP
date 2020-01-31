---
title: プリミティブ操作カウンター |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 1f554c0a1b92c8f6b59be3a9d9965e0e25bd074f
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820421"
---
# <a name="primitive-operations-counter"></a>プリミティブ操作カウンター  

`Primitive Operations Counter` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。 クォンタムプログラムで呼び出されたすべての操作で使用されるプリミティブ実行の数をカウントします。 `Microsoft.Quantum.Intrinsic` からのすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。 収集された統計情報は、操作呼び出しグラフの端に集計されます。 ここで、`CCNOT` 操作を実装するために必要な `T` ゲートの数をカウントします。 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>C#プログラム内でのプリミティブ操作カウンターの使用

`CCNOT` 実際に 7 `T` ゲートが必要であり、8 `T` ゲートを実行する `ApplySampleWithCCNOT` であることC#を確認するには、次のコードを使用します。

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

プログラムの最初の部分は `ApplySampleWithCCNOT`を実行します。 2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、`ApplySampleWithCCNOT`によって実行される T ゲートの数を取得します。 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

2つの型パラメーターを指定して `GetMetric` を呼び出すと、特定の呼び出し先に関連付けられているメトリックの値が返されます。 この例の操作では `Primitive.CCNOT` が `ApplySampleWithCCNOT` 内で呼び出されるため、呼び出し先には `<Primitive.CCNOT, ApplySampleWithCCNOT>`エッジが含まれます。 

使用される `CNOT` ゲートの数を取得するには、次の行を追加します。
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最後に、ゲートカウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
