---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfae01d11524f64ceebd53aa8544d7ea48c40f31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818684"
---
# <a name="r1frac-operation"></a>R1Frac 操作

名前空間: [Microsoft. Quantum. 組み込み](xref:Microsoft.Quantum.Intrinsic)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


{1}Dyadic の割合として指定された角度で、$ \ket $ 状態に関する回転を適用します。

\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \ pi k/2 ^ n})。
\end{align}

> [!WARNING]
> この操作では、とは **逆** の符号規則を使用 @"microsoft.quantum.intrinsic.r" し、に含まれる $ 1/2 $ の係数は含まれません @"microsoft.quantum.intrinsic.r1" 。

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="numerator--int"></a>分子: [Int](xref:microsoft.quantum.lang-ref.int)

Qubit を回転する角度の、dyadic の分数表現の分子。


### <a name="power--int"></a>power: [Int](xref:microsoft.quantum.lang-ref.int)

Qubit を回転する角度の分母を指定する2の累乗。


### <a name="qubit--qubit"></a>qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

ゲートを適用する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

次と同じです。

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```