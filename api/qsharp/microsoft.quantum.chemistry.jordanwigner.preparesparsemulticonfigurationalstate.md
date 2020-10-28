---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSparseMultiConfigurationalState
title: PrepareSparseMultiConfigurationalState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSparseMultiConfigurationalState
qsharp.summary: Sparse multi-configurational state preparation of trial state by adding excitations to initial trial state.
ms.openlocfilehash: 1182f79a33784cdb49cb13db5cc97a0a45e59f9f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713848"
---
# <a name="preparesparsemulticonfigurationalstate-operation"></a>PrepareSparseMultiConfigurationalState 操作

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


Excitations を初期評価版に追加することによって、評価版の複数のスパースな状態を準備します。

```qsharp
operation PrepareSparseMultiConfigurationalState (initialStatePreparation : (Qubit[] => Unit), excitations : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="initialstatepreparation--qubit--unit"></a>initialStatePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

初期評価の状態を準備するためのユニタリ。


### <a name="excitations--jordanwignerinputstate"></a>excitations: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]

励起の振幅と、励起が作用する qubit インデックスによって表される初期評価状態の Excitations。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian の qubits。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

