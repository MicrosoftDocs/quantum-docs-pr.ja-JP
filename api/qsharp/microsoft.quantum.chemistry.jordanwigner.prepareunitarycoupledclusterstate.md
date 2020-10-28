---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareUnitaryCoupledClusterState
title: PrepareUnitaryCoupledClusterState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareUnitaryCoupledClusterState
qsharp.summary: Unitary coupled-cluster state preparation of trial state
ms.openlocfilehash: 4db31e3e79d27f12178dbf121cd04727c2332c62
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713825"
---
# <a name="prepareunitarycoupledclusterstate-operation"></a>PrepareUnitaryCoupledClusterState 操作

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


インライン結合-評価状態のクラスター状態準備

```qsharp
operation PrepareUnitaryCoupledClusterState (initialStatePreparation : (Qubit[] => Unit), clusterOperator : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], trotterStepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="initialstatepreparation--qubit--unit"></a>initialStatePreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) 

初期評価の状態を準備するためのユニタリ。


### <a name="clusteroperator--jordanwignerinputstate"></a>clusterOperator: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]




### <a name="trotterstepsize--double"></a>trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian の qubits。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

