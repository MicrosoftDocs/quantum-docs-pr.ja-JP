---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818869"
---
# <a name="m-operation"></a>M 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


P$Z $ ベースで1つの qubit の測定を実行します。

出力結果は、distribution \begin{align} (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. によって得られます。
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>入力

### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

測定する qubit。



## <a name="output--__invalidresult__"></a>出力:__無効 <Result>__

`Zero` $ + $1 eigenvalue が観測されている場合は、 `One` $-$1 eigenvalue が観測されている場合はです。

## <a name="remarks"></a>解説

次と同じです。

```qsharp
Measure([PauliZ], [qubit]);
```