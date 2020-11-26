---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: _flipToBasis 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: 1581a1267902ceee81d6f01348f4ee718e49ee47
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223988"
---
# <a name="_fliptobasis-operation"></a>_flipToBasis 操作

名前空間: [Microsoft... 診断](xref:Microsoft.Quantum.Diagnostics)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


$ \Ket {0} \otimes\cdots\ket {0} $ を $ \ket{\ psi_0} \ otimes \ket{\ psi_ {n-1}} $ にマップする unitaries 適用します。 $ \ket{\ psi_k} $ は、に依存 `basis[k]` します。

`basis[k]`と $ \ket{\ psi_k} $ の値の対応は次のとおりです。

- `basis[k]=0` $ \rightarrow \ket {0} $。
- `basis[k]=1` $ \rightarrow \ket {1} $。
- `basis[k]=2` $ \rightarrow \ket{+} $。
- `basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate of P# li Y)。

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="basis--int"></a>ベース: [Int](xref:microsoft.quantum.lang-ref.int)[]

Qubit の各要素に1つずつ、単一の qubit basis 状態 Id の配列 (0 <= id <= 3)。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

操作する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

