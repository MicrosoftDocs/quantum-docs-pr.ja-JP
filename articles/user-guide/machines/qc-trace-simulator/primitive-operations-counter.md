---
title: プリミティブ操作カウンター
description: Microsoft QDK プリミティブ操作カウンターについて説明します。このカウンターは、クォンタムプログラムでの操作によって使用されるプリミティブ実行の数を追跡します。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275559"
---
# <a name="primitive-operations-counter"></a>プリミティブ操作カウンター  

は、 `Primitive Operations Counter` quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。 クォンタムプログラムで呼び出されたすべての操作で使用されるプリミティブ実行の数をカウントします。 からのすべての操作 `Microsoft.Quantum.Intrinsic` は、単一の qubit 回転、T ゲート、単一の Qubit Clifford ゲート、CNOT ゲート、およびマルチ Qubit pobservable li の測定値で表現されます。 収集された統計情報は、操作呼び出しグラフの端に集計されます。 ここで `T` 、操作を実装するために必要なゲートの数をカウント `CCNOT` します。 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>C# プログラム内でのプリミティブ操作カウンターの使用

`CCNOT`実際に7ゲートが必要で、8ゲートを実行することを確認するに `T` `ApplySampleWithCCNOT` `T` は、次の C# コードを使用できます。

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

プログラムの最初の部分が実行さ `ApplySampleWithCCNOT` れます。 2番目の部分では、メソッドを使用し `QCTraceSimulator.GetMetric` て、によって実行される T ゲートの数を取得し `ApplySampleWithCCNOT` ます。 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

`GetMetric`2 つの型パラメーターを指定してを呼び出すと、特定の呼び出し先に関連付けられているメトリックの値が返されます。 この例で `Primitive.CCNOT` は、操作は内で呼び出される `ApplySampleWithCCNOT` ため、呼び出しグラフにはエッジが含まれ `<Primitive.CCNOT, ApplySampleWithCCNOT>` ます。 

使用されるゲートの数を取得するに `CNOT` は、次の行を追加します。
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最後に、ゲートカウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
