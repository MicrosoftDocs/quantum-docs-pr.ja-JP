---
title: Width カウンタ |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820370"
---
# <a name="width-counter"></a>幅カウンター

`Width Counter` は、各操作によって割り当てられて借用される qubits の数をカウントします。
`Microsoft.Quantum.Intrinsic` 名前空間のすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。 一部のプリミティブ操作では、追加の qubits を割り当てることができます。 たとえば、制御された `X` ゲートまたは制御された `T` ゲートを乗算します。 制御された複数の `X` ゲートの実装によって割り当てられた追加の qubits を計算してみましょう。

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>C#プログラム内での Width カウンターの使用

合計5つの qubits に対して作用する制御 `X` の乗算では、2つの補助 qubits が割り当てられ、その入力幅は5になります。 このことを確認するには、次C#のプログラムを使用します。

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

プログラムの最初の部分は `ApplyMultiControlledX`を実行します。 2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、割り当てられた qubits の数と、制御 `X` が入力として受け取った qubits の数を取得します。 

最後に、width カウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
