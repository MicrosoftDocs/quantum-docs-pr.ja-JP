---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: _ApplyJordanWignerZTerm_ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: f42c2ba7570f32d3f26ff82dd4a0ee6f9677fa30
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714730"
---
# <a name="_applyjordanwignerzterm_-operation"></a>_ApplyJordanWignerZTerm_ 操作

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


によって記述された Z 語による時間の推移を適用 `GeneratorIndex` します。

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="term--generatorindex"></a>用語: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` Z 語を表す。


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

時間の進化の期間。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian の qubits。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

