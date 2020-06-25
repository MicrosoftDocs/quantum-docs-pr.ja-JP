---
title: 幅カウンター
description: クォンタムプログラムの各操作によって割り当てられた qubits の数をカウントする Microsoft QDK Width カウンターについて説明します。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275560"
---
# <a name="width-counter"></a>幅カウンター

は、 `Width Counter` 各操作によって割り当てられて借用される qubits の数をカウントします。
名前空間のすべて `Microsoft.Quantum.Intrinsic` の操作は、単一の qubit 回転、T ゲート、単一の Qubit Clifford ゲート、CNOT ゲート、およびマルチ Qubit pobservable li の測定値で表現されます。 一部のプリミティブ操作では、追加の qubits を割り当てることができます。 たとえば、制御 `X` ゲートまたは制御さ `T` れたゲートを乗算します。 次に、乗算制御ゲートの実装によって割り当てられた追加の qubits の数を計算してみましょう `X` 。

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>C# プログラム内での Width カウンターの使用

`X`合計5つの qubits に対して制御される演算を乗算すると、2つの補助 qubits が割り当てられ、その入力幅は5になります。 このことを確認するには、次の C# プログラムを使用できます。

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

プログラムの最初の部分が実行さ `ApplyMultiControlledX` れます。 2番目の部分では、メソッドを使用して、 `QCTraceSimulator.GetMetric` 割り当てられた qubits と、 `X` 入力として受信された qubits の数を取得します。 

最後に、width カウンターによって収集されたすべての統計を CSV 形式で出力するには、次のようにします。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
