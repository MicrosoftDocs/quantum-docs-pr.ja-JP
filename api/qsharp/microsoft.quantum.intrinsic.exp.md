---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819008"
---
# <a name="exp-operation"></a>Exp 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


マルチ qubit の P# li 演算子の指数を適用します。

\begin{align} e ^ {i/シータ [P_0/otimes P_1/cドット P_ {N-1}]}, \end{align} ここで $P _i $ はの $i $ th 要素、 `paulis` where $N = $ `Length(paulis)` です。

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="paulis--pauli"></a>paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]

各 qubit の最新の製品要素を示す single qubit の値の配列。


### <a name="theta--double"></a>シータ: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットレジスタのローテーションに使用する、指定されたマルチ qubit の P# li 演算子に関する角度。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

指定された回転をに適用するために登録します。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

