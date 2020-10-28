---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSingleConfigurationalStateSingleSiteOccupation
title: PrepareSingleConfigurationalStateSingleSiteOccupation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSingleConfigurationalStateSingleSiteOccupation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: de385b7ffd76c1deaa41cf0cd3338d3243feb1fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713867"
---
# <a name="preparesingleconfigurationalstatesinglesiteoccupation-operation"></a>PrepareSingleConfigurationalStateSingleSiteOccupation 操作

名前空間: [JordanWigner。](xref:Microsoft.Quantum.Chemistry.JordanWigner)

パック [](https://nuget.org/packages/)


スピン orbitals を利用して、評価版の状態を簡単に準備

```qsharp
operation PrepareSingleConfigurationalStateSingleSiteOccupation (qubitIndices : Int[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="qubitindices--int"></a>qubitIndices: [Int](xref:microsoft.quantum.lang-ref.int)[]

原子によって占有される qubits のインデックス。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

Hamiltonian の qubits。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

