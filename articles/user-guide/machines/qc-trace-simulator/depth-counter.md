---
title: 深さカウンター
description: クォンタムプログラムで呼び出されたすべての操作の深さのカウントを収集する Microsoft QDK の深さカウンターについて説明します。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: 0029a00e6a3563dc542daeda2afa7cabf42441fb
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415266"
---
# <a name="depth-counter"></a>深さカウンター

は、 `Depth Counter` quantum コンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の一部です。
これは、クォンタムプログラムで呼び出された各操作の深さの下限を表すカウントを収集するために使用されます。 からのすべての操作 <xref:microsoft.quantum.intrinsic> は、単一の qubit 回転、T ゲート、単一の Qubit Clifford ゲート、CNOT ゲート、およびマルチ Qubit pobservable li の測定値で表現されます。 ユーザーは、のフィールドを使用して、各プリミティブ操作の深さを設定でき `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> ます。

既定では、すべての操作の深さは 0 (深度1を持つ T ゲートを除く) です。 つまり、既定では、演算の T の深さのみが計算されます (これが望ましい場合があります)。 収集された統計情報は、操作呼び出しグラフのすべての端に集計されます。 

次に、操作の深さを計算してみましょう <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.ccnot> 。 次の Q # サンプルコードを使用します。

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>C# プログラム内での Depth カウンターの使用

深さが5で、深さが6であることを確認するに `CCNOT` `T` `ApplySampleWithCCNOT` `T` は、次の C# コードを使用できます。

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

プログラムの最初の部分が実行さ `ApplySampleWithCCNOT` れます。 2番目の部分では、メソッドを使用し `QCTraceSimulator.GetMetric` `T` て、との深さを取得し `CCNOT` `ApplySampleWithCCNOT` ます。 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

最後に、によって収集されたすべての統計を CSV 形式で出力するには、次のようにします `Depth Counter` 。
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>関連項目 ##

- クォンタムコンピューターの[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)の概要。
