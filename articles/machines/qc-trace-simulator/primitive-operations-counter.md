---
title: プリミティブ操作カウンター |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: クォンタムコンピューターのトレースシミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184884"
---
# <a name="primitive-operations-counter"></a>プリミティブ操作カウンター  

`Primitive Operations Counter` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。 クォンタムプログラムで呼び出されたすべての操作で使用されるプリミティブ実行の数をカウントします。 `Microsoft.Quantum.Primitive` からのすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。 収集された統計情報は、操作呼び出しグラフの端に集計されます。 ここで、`CCNOT` 操作を実装するために必要な `T` ゲートの数をカウントします。 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>C#プログラム内でのプリミティブ操作カウンターの使用

`CCNOT` 実際に 7 `T` ゲートが必要であり、8 `T` ゲートを実行する `CCNOTDriver` であることC#を確認するには、次のコードを使用します。

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

プログラムの最初の部分は `CCNOTDriver`を実行します。 2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、`CCNOTDriver`によって実行される T ゲートの数を取得します。 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

2つの型パラメーターを指定して `GetMetric` を呼び出すと、特定の呼び出し先に関連付けられているメトリックの値が返されます。 この例の操作では `Primitive.CCNOT` が `CCNOTDriver` 内で呼び出されるため、呼び出し先には `<Primitive.CCNOT,CCNOTDriver>`エッジが含まれます。 

使用される `CNOT` ゲートの数を取得するには、次の行を追加します。
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

最後に、ゲートカウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
