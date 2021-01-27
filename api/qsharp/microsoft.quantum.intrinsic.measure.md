---
uid: Microsoft.Quantum.Intrinsic.Measure
title: Measure 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: bf0a606b1bfc8c4762245422450ec26907ec1946
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818766"
---
# <a name="measure-operation"></a>Measure 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定した基底クラスの1つ以上の qubits の結合測定を実行します。

出力結果は、ディストリビューションによって得られます。 \begin{align} \ Pr (\texttt{Zero} | \ket{\psi}) = \frac12 \braket{/psi \ mid | \ left (\ done + P_0/otimes P_ {N-1} > right) \ mid P_1 |-psi}、\end{align} where $P _i $ は、の $i $ th 要素、 `bases` where $N = \texttt{Length} (\texttt{bases}) $ となります。
つまり、測定された `Result` 測定効果の eigenvalue が $ (-1) ^ d $ であるように、測定値は $ $d $ を返します。

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>入力

### <a name="bases--pauli"></a>ベース: [P# li](xref:microsoft.quantum.lang-ref.pauli)[]

各 qubit の最新の製品要素を示す single qubit の値の配列。


### <a name="qubits--qubit"></a>qubits: [qubits](xref:microsoft.quantum.lang-ref.qubit)[]

測定する qubits のレジスタ。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

`Zero` $ + $1 eigenvalue が観測されている場合は、 `One` $-$1 eigenvalue が観測されている場合はです。

## <a name="remarks"></a>解説

Basis 配列と qubit 配列の長さが異なる場合、操作は失敗します。