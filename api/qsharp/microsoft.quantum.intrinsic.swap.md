---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: スワップ操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: e93c976f2fdf02de77fafa4d22e95fe9a33a9ba6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198420"
---
# <a name="swap-operation"></a>スワップ操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


スワップゲートを qubits のペアに適用します。

\begin{align} \ \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 0 \\ \\ & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}、\end{align}

ここでは、行と列は、クォンタムの概念ガイドのとおりに並べられています。

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="qubit1--qubit"></a>qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

交換する最初の qubit。


### <a name="qubit2--qubit"></a>qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

スワップする2番目の qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

次と同じです。

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```