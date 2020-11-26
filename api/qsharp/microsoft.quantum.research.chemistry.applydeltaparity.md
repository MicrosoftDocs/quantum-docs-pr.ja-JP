---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: 40157b6a166b09c6fee63d86e203f92069d008f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225756"
---
# <a name="applydeltaparity-operation"></a>ApplyDeltaParity 操作

名前空間: [Microsoft. Quantum. 化学](xref:Microsoft.Quantum.Research.Chemistry)

パッケージ: [Microsoft. Quantum. 化学](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


前の PQRS 間のパリティの差を計算します...用語と次の PQRS...句. この違いは補助 qubit で計算されます。

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
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