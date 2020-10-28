---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711524"
---
# <a name="exp-operation"></a>Exp 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


マルチ qubit の P# li 演算子の指数を適用します。

\begin{align} e ^ {i/シータ [P_0/otimes P_1/cドット P_ {N-1}]}, \end{align} ここで $P _i $ はの $i $ th 要素、 `paulis` where $N = $ `Length(paulis)` です。

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="paulis--pauli"></a>paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]

各 qubit の最新の製品要素を示す single qubit の値の配列。


### <a name="theta--double"></a>シータ: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットレジスタのローテーションに使用する、指定されたマルチ qubit の P# li 演算子に関する角度。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

指定された回転をに適用するために登録します。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

