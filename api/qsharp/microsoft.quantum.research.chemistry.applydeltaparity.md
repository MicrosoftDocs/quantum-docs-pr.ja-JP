---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723979"
---
# <a name="applydeltaparity-operation"></a>ApplyDeltaParity 操作

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)

パック [](https://nuget.org/packages/)


前の PQRS 間のパリティの差を計算します...用語と次の PQRS...句. この違いは補助 qubit で計算されます。

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="prevfermionicterm--int"></a>Prevterm: [Int](xref:microsoft.quantum.lang-ref.int)[]

以前の PQRS に対するインデックスの一覧...条項.


### <a name="nextfermionicterm--int"></a>Nextの Mimionicterm: [Int](xref:microsoft.quantum.lang-ref.int)[]

次の PQRS へのインデックスの一覧...条項.


### <a name="aux--qubit"></a>aux: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

パリティ計算の結果が格納される補助 qubit。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

すべての PQRS によって処理された qubit...条項.



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

これは、P < Q < R < S のインデックスが < していることを前提としています...prevPQ と nextPQ の両方。