---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720938"
---
# <a name="m-operation"></a>M 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


P$Z $ ベースで1つの qubit の測定を実行します。

出力結果は、distribution \begin{align} (\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. によって得られます。
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>入力

### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

測定する qubit。



## <a name="output--__invalidresult__"></a>出力: __無効 <Result>__

`Zero` $ + $1 eigenvalue が観測されている場合は、 `One` $-$1 eigenvalue が観測されている場合はです。

## <a name="remarks"></a>解説

次と同じです。

```qsharp
Measure([PauliZ], [qubit]);
```