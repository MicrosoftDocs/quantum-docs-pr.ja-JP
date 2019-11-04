---
title: 深さカウンター |クォンタムコンピューターのトレースシミュレーター |Microsoft Docs
description: クォンタムコンピューターのトレースシミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184901"
---
# <a name="depth-counter"></a>深さカウンター

`Depth Counter` は、クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)に含まれています。
これは、クォンタムプログラムで呼び出されたすべての操作の深さのカウントを収集するために使用されます。 <xref:microsoft.quantum.intrinsic> からのすべての操作は、単一の qubit 回転、T ゲート、単一の qubit Clifford ゲート、CNOT ゲート、およびマルチ qubit Pobservable Li の測定値で表現されます。 ユーザーは、<xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>の [`gateTimes`] フィールドを使用して、各プリミティブ操作の深さを設定できます。

既定では、すべての操作の深さは 0 (深度1を持つ T ゲートを除く) です。 つまり、既定では、演算の T の深さのみが計算されます (これが望ましい場合があります)。 収集された統計情報は、操作呼び出しグラフのすべての端に集計されます。 

ここで、<xref:microsoft.quantum.intrinsic.ccnot> 操作の <xref:microsoft.quantum.intrinsic.t> の深さを計算してみましょう。 次の Q # ドライバーコードを使用します。 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>C#プログラム内での Depth カウンターの使用

`CCNOT` に `T` 深度5があり、`CCNOTDriver` に `T` 深さ6があることを確認するC#には、次のコードを使用します。

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

プログラムの最初の部分は `CCNOTDriver`を実行します。 2番目の部分では、メソッド `QCTraceSimulator.GetMetric` を使用して、`CCNOT` と `CCNOTDriver`の `T` の深さを取得します。 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

最後に、`Depth Counter` によって収集されたすべての統計を CSV 形式で出力するには、次のようにします。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
