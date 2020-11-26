---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Rz 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: d637abf3562eb60705da517467939dc588229c39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198624"
---
# <a name="rz-operation"></a>Rz 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された角度で $z $ 軸についての回転を適用します。

\begin{align} R_z (\ シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_z/2} = \begin{bmatrix} e ^ {-i \ シータ/2} & 0 \\ \\ 0 & e ^ {i/シータ/2} \end{bmatrix}.
\end{align}

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="theta--double"></a>シータ: [Double](xref:microsoft.quantum.lang-ref.double)

Qubit を回転する角度。


### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ゲートを適用する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

次と同じです。

```qsharp
R(PauliZ, theta, qubit);
```