---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: f5f1d74274994f042f1bc3f2e0d5332f504be02c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851110"
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