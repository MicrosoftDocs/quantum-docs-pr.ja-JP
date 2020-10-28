---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725323"
---
# <a name="trotterstepimpl-operation"></a>TrotterStepImpl 操作

名前空間: [Microsoft. Quantum. シミュレーション](xref:Microsoft.Quantum.Simulation)

パック [](https://nuget.org/packages/)


に含まれる用語によって時間の進化を実装 `GeneratorSystem` します。

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator: [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

シミュレートするシステムの完全な説明。


### <a name="idx--int"></a>idx: [Int](xref:microsoft.quantum.lang-ref.int)

説明されたシステム内の用語への整数インデックス。


### <a name="stepsize--double"></a>stepsize: [Double](xref:microsoft.quantum.lang-ref.double)

によってインデックスが作成された期間の時間の乗数 `idx` 。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

シミュレーションによって処理された qubits。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

