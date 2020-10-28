---
uid: Microsoft.Quantum.Intrinsic.Ry
title: 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720007"
---
# <a name="ry-operation"></a>操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


指定された角度で $y $ 軸についての回転を適用します。

\begin{align} R_y (-シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_y/2} = \begin{bmatrix}/cos \frac{\theta} {2} &-\ sin \frac{\theta}/ {2} \\ \\ sin \frac{\theta} {2} & \ cos \frac{\theta} {2} \end{bmatrix}.  
\end{align}

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
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
R(PauliY, theta, qubit);
```