---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: 操作の実行
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711487"
---
# <a name="expfrac-operation"></a>操作の実行

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


Dyadic の分数で指定された引数を使用して、マルチ qubit の P# li 演算子の指数を適用します。

\begin{align} e ^ {i \ pi k [P_0/otimes P_1/cドット P_ {N-1}]/2 ^ N}、\end{align} where $P _i $ はの $i $ th 要素、 `paulis` where $N = $ `Length(paulis)` です。

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a>入力

### <a name="paulis--pauli"></a>paulis: [p li](xref:microsoft.quantum.lang-ref.pauli)[]

各 qubit の最新の製品要素を示す single qubit の値の配列。


### <a name="numerator--int"></a>分子: [Int](xref:microsoft.quantum.lang-ref.int)

Qubit レジスタを回転する角度の、dyadic の分数表現の分子 ($k $)。


### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)

Qubit レジスタを回転する角度の分母を指定する2の累乗 ($n $)。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

指定された回転をに適用するために登録します。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

