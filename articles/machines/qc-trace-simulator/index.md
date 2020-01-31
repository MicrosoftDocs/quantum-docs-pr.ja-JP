---
title: 量子コンピューターのトレース シミュレーター | Microsoft Docs
description: 量子コンピューターのトレース シミュレーターの概要
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 929745a6da6034599e97d2f573190308fde6eb75
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820438"
---
# <a name="quantum-trace-simulator"></a>量子トレース シミュレーター

Microsoft 量子コンピューターのトレース シミュレーターは、量子コンピューターの状態を実際にシミュレートせずに、量子プログラムを実行します。  このため、トレース シミュレーターでは、何千もの量子ビットを使用する量子プログラムを実行できます。  これは主に次の 2 つの目的で役立ちます。 

* 量子プログラムの一部である、従来型のコードのデバッグ。 
* 量子プログラムの特定のインスタンスを量子コンピューターで実行するために必要なリソースの推定。

トレース シミュレーターは、測定を行う必要がある場合に、ユーザーによって提供される追加情報を使用します。 詳細については、「[測定結果の確率を指定する](#providing-the-probability-of-measurement-outcomes)」セクションを参照してください。 

## <a name="providing-the-probability-of-measurement-outcomes"></a>測定結果の確率を指定する

量子アルゴリズムには、2 種類の測定値が表示されます。 最初の種類は、ユーザーが結果の確率を知っている場合に使用するため、補助的な役割を果たします。 この場合、ユーザーは <xref:microsoft.quantum.intrinsic> 名前空間の <xref:microsoft.quantum.intrinsic.assertprob> を使用して、知っている確率を表すことができます。 次の例を使って説明します。

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

トレース シミュレーターが `AssertProb` を実行すると、`source` と `q` で `PauliZ` を測定した結果は、確率が0.5 の `Zero` となることを記録します。 シミュレーターが後で `M` を実行すると、記録された結果の確率の値が検出され、`M` は確率が0.5 の `Zero` または `One` を返します。 量子状態を追跡するシミュレーターで同じコードを実行すると、シミュレーターは `AssertProb` で指定された確率が正しいかどうかを確認します。

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>量子コンピューターのトレース シミュレーターを使用してプログラムを実行する 

量子コンピューターのトレース シミュレーターは、ターゲット コンピューターの 1 つとして見なすことができます。 量子コンピューターを使用するための C# ドライバー プログラムは、他の量子シミュレーターで使用するものとよく似ています。 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

`AssertProb` によって注釈が付けられていない測定が少なくとも 1 つある場合は、シミュレーターによって `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` 名前空間から `UnconstrainedMeasurementException` がスローされることに注意してください。 詳細については [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) に関する API ドキュメントを参照してください。

量子プログラムの実行に加えて、トレース シミュレーターには、プログラム内のバグを検出し、量子プログラム リソースの推定を行うための 5 つのコンポーネントが付属しています。 

* [Distinct Inputs Checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [Invalidated Qubits Use Checker](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [Primitive Operations Counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [Circuit Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [Circuit Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

これらの各コンポーネントは、`QCTraceSimulatorConfiguration` で適切なフラグを設定することによって有効にすることができます。 これらの各コンポーネントの使用方法の詳細については、対応する参照ファイルを参照してください。 具体的な詳細については [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) に関する API ドキュメントを参照してください。

## <a name="see-also"></a>参照
量子コンピューターの[トレース シミュレーター](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)向け C# リファレンス 

