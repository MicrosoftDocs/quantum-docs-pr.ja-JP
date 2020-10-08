---
title: 量子トレース シミュレーター - Quantum Development Kit
description: Microsoft の量子コンピューター トレース シミュレーターを使用して、従来型のコードをデバッグし、Q# プログラムのリソース要件を見積もる方法について説明します。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7f5e25aa7b58277642783e03d03854cd75ff4ca3
ms.sourcegitcommit: d98190988ff03146d9ca2b0d325870cd717d729a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91771287"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Microsoft Quantum Development Kit (QDK) の量子トレース シミュレーター

QDK の <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> クラスでは、量子コンピューターの状態を実際にシミュレーションすることなく量子プログラムが実行されます。 このため、量子トレース シミュレーターでは、何千もの量子ビットを使用する量子プログラムを実行できます。  これは主に次の 2 つの目的で役立ちます。 

* 量子プログラムの一部である、従来型のコードのデバッグ。 
* 量子プログラムの特定のインスタンスを量子コンピューターで実行するために必要なリソースの推定。 実際、より限定されたメトリック セットを提供する[リソース推定器](xref:microsoft.quantum.machines.resources-estimator)は、トレース シミュレーターに基づいて構築されています。

## <a name="invoking-the-quantum-trace-simulator"></a>量子トレース シミュレーターの呼び出し

量子トレース シミュレーターを使用して、任意の Q# 操作を実行できます。

他のターゲット マシンと同様に、最初に `QCTraceSimulator` クラスのインスタンスを作成し、それを操作の `Run` メソッドの最初のパラメーターとして渡します。

`QuantumSimulator` クラスとは異なり、`QCTraceSimulator` クラスでは <xref:System.IDisposable> インターフェイスが実装されていないため、これを `using` ステートメント内で囲む必要はありません。

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>測定結果の確率を指定する

量子トレース シミュレーターでは実際の量子状態がシミュレートされないため、操作内の測定結果の確率を計算することはできません。 

したがって、操作に測定が含まれている場合は、<xref:microsoft.quantum.diagnostics> 名前空間の <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 操作を使用して、これらの確率を明示的に指定する必要があります。 次の例を使って説明します。

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

量子トレース シミュレーターで `AssertMeasurementProbability` が発生すると、`source` と `q` で `PauliZ` を測定した結果は、確率 **0.5** で `Zero` となることが記録されます。 その後 `M` 操作が実行されると、結果の確率の記録された値が検出され、`M` は、確率 **0.5** で `Zero` または `One` を返します。 量子状態を追跡するシミュレーターで同じコードを実行すると、シミュレーターは `AssertMeasurementProbability` で指定された確率が正しいかどうかを確認します。

`AssertMeasurementProbability` によって注釈が付けられていない操作が少なくとも 1 つある場合は、シミュレーターによって [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception) がスローされることに注意してください。

## <a name="quantum-trace-simulator-tools"></a>量子トレース シミュレーターのツール

QDK には、プログラム内のバグを検出し、量子プログラム リソースの見積もりを実行するために、量子トレース シミュレーターで使用できる 5 つのツールが用意されています。 

|ツール | 説明 |
|-----| -----|
|[個別入力チェッカー](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |共有量子ビットと競合する可能性があるかどうかを確認します |
|[無効な量子ビット使用チェッカー](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |プログラムが既に解放されている量子ビットに操作を適用していないかどうかを確認します |
|[プリミティブ操作カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | 量子プログラムで呼び出されたすべての操作によって使用されるプリミティブの数をカウントします  |
|[深さのカウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |量子プログラムで呼び出された各操作の深さの下限を表すカウントを収集します   |
|[幅のカウンター](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |量子プログラムの各操作によって割り当てられ、借用された量子ビットの数をカウントします |

これらの各ツールは、`QCTraceSimulatorConfiguration` で適切なフラグを設定し、構成を `QCTraceSimulator` 宣言に渡すことによって有効になります。 これらの各ツールの使用方法の詳細については、前の一覧のリンクを参照してください。 `QCTraceSimulator` の構成の詳細については、「[QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)」を参照してください。

## <a name="qctracesimulator-methods"></a>QCTraceSimulator のメソッド

`QCTraceSimulator` には、量子操作中に追跡されるメトリックの値を取得するための組み込みメソッドがいくつか用意されています。 [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) と [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) メソッドの例については、[プリミティブ操作カウンター](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)、[深さのカウンター](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)、および[幅のカウンター](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)に関する記事を参照してください。 使用可能なすべてのメソッドの詳細については、Q# API リファレンスの [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) を参照してください。  

## <a name="see-also"></a>関連項目

- [量子リソース推定器](xref:microsoft.quantum.machines.resources-estimator)
- [量子 Toffoli シミュレーター](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子完全状態シミュレーター](xref:microsoft.quantum.machines.full-state-simulator) 