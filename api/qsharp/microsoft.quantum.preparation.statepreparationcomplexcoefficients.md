---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 1d0efa7b83d2e8e75c4b293866f3929f357ec44b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210371"
---
# <a name="statepreparationcomplexcoefficients-function"></a>StatePreparationComplexCoefficients 関数

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> StatePreparationComplexCoefficients は非推奨となりました。 代わりに、<xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> を使用してください。

特定のクォンタム状態を準備する操作を返します。

返された操作 $U $ は、複雑な $r 係数を持つ任意のクォンタム状態 $ \ket{\psi} $ を、$n $-qubit 計算ベースの状態 $ \ket{0...0} $ から _j e ^ {i t_j} $ に準備します。

新しく割り当てられたレジスタに対する U のアクションは、$ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}} によって指定されます。
\end{align} $ $

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a>入力

### <a name="coefficients--complexpolar"></a>係数: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

絶対値とフェーズ $ (r_j、t_j) $ で表される、最大 $ 2 ^ n $ の複合係数の配列。 $J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。



## <a name="output--littleendian--unit--is-adj--ctl"></a>出力: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl

状態の準備のためのユニタリ操作 $U $ です。

## <a name="remarks"></a>解説

負の入力係数 $r _j < $0 は、値 $ | r_j | $ を持つ正の値として処理されます。 `coefficients` $ 2 ^ n $ 未満の場合は、要素 $ (r_j、t_j) = (0.0, 0.0) $ が埋め込まれます。