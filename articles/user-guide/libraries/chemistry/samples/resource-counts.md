---
title: リソース数の取得
description: クォンタムトレースシミュレーターを使用してリソースの見積もりを取得する方法について説明します。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: 35c16e622a390b730ad7385efcc365c212e981fe
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869326"
---
# <a name="obtaining-resource-counts"></a>リソース数の取得

従来のコンピューターで $n $ qubits をシミュレートするコストは、$n $ を使用して指数関数的に拡大できます。 これにより、完全な状態シミュレーターで実行できる量子化学シミュレーションのサイズが大幅に制限されます。 しかし、大規模な化学インスタンスの場合は、役に立つ情報が得られる可能性があります。 ここでは、[トレースシミュレーター](xref:microsoft.quantum.machines.qc-trace-simulator.intro)を使用して、化学をシミュレートするための T ゲートや cnot ゲートの数などのリソースコストを自動で取得する方法について説明します。 このような情報は、quantum のコンピューターがこれらの quantum の化学アルゴリズムを実行するのに十分な大きさであることが通知されます。 参考のために、提供されているサンプルを参照してください `GetGateCount` 。

`FermionHamiltonian`たとえば、「[ファイルからの読み込み](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)」の例で説明したように、Broombridge スキーマから読み込まれたインスタンスが既に存在するとします。 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

リソースの推定値を取得するための構文は、完全な状態シミュレーターでアルゴリズムを実行することとほぼ同じです。 別のターゲットコンピューターを選択するだけです。 リソースの推定のために、1つの Trotter ステップのコスト、または Qubitization 手法によって作成されたクォンタムウォークを評価することができます。 これらのアルゴリズムを呼び出すための定型句は次のとおりです。

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

ここで、トレースシミュレーターを構成して、関心のあるリソースを追跡します。 この例では、フラグをに設定することによって、プリミティブなクォンタム操作をカウントし `usePrimitiveOperationsCounter` `true` ます。 技術的な詳細をに設定すると、 `throwOnUnconstraintMeasurement` `false` コードが Q# 測定結果の確率を正しくアサートできない場合に、例外が発生しないようにすることができます。

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

次のように、ドライバープログラムからクォンタムアルゴリズムを実行します。

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```