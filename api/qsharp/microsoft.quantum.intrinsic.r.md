---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720931"
---
# <a name="r-operation"></a>R 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

パック [](https://nuget.org/packages/)


指定された P# li 軸についての回転を適用します。

\begin{align} R_ {\ mu} (\ シータ) \mathrel{: =} e ^ {-i \ シータ \ sigma_ {/mu}/2}、\end{align} where $ \ mu \ \{ i, X, Y, Z \} $ です。

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="pauli--pauli"></a>p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li

回転を形成するために累乗される p# li 演算子 ($ \ mu $)。


### <a name="theta--double"></a>シータ: [Double](xref:microsoft.quantum.lang-ref.double)

Qubit を回転する角度。


### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ゲートを適用する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

で呼び出された場合 `pauli = PauliI` 、この操作は *グローバルフェーズ* を適用します。 このフェーズは、ファンクタで使用する場合に重要になり `Controlled` ます。