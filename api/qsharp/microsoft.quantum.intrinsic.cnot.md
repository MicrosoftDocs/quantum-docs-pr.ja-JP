---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 90e84f7d0ea7373498632474dfafa23335f0c78e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198978"
---
# <a name="cnot-operation"></a>CNOT 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


制御されていない (CNOT) ゲートを qubits のペアに適用します。

\begin{align} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 & \\ \\ 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}、\end{align} です。

ここでは、行と列は、クォンタムの概念ガイドのとおりに並べられています。

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="control--qubit"></a>コントロール: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

CNOT gate の制御 qubit。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

CNOT gate のターゲット qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

次と同じです。

```qsharp
Controlled X([control], target);
```