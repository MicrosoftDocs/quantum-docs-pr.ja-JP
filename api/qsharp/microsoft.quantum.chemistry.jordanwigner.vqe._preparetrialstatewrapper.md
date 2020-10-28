---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: _prepareTrialStateWrapper 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: bfd7b9ce8e8b2c8f322d676c640f8c2488655516
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713764"
---
# <a name="_preparetrialstatewrapper-operation"></a>_prepareTrialStateWrapper 操作

名前空間: [JordanWigner です。 VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

パック [](https://nuget.org/packages/)


Adjoint を定義することで、EstimateFrequencyA との互換性を確保するための PrepareTrialState のプライベートラッパー。
EstimateFrequencyA には、QuantumSimulator を対象とする組み込みのエミュレーション機能があり、実行速度が上がります。

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="inputstate--intjordanwignerinputstate"></a>inputState: ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])

PrepareTrialState を実行するために必要な Jordan-Wigner 入力です。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

