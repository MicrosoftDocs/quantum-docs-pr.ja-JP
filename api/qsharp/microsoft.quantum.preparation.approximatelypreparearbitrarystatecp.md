---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP
title: ApproximatelyPrepareArbitraryStateCP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateCP
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 44352a4d6325c128539351695fb14d3706ce842f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226538"
---
# <a name="approximatelypreparearbitrarystatecp-operation"></a>ApproximatelyPrepareArbitraryStateCP 操作

名前空間: [Microsoft. Quantum](xref:Microsoft.Quantum.Preparation)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


係数とリトルエンディアンでエンコードされたクォンタムレジスタを指定すると、は指定された係数によって示されるレジスタの状態を、指定された近似値に設定します。

```qsharp
operation ApproximatelyPrepareArbitraryStateCP (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作では $n、_j e ^ {i t_j} $ から \ket{\psi} $-qubit コンピューティングベースの状態 $ \ket{0/cドット 0} $ から、複雑な $r 係数を持つ任意のクォンタム状態 $ $ を準備します。
具体的には、この操作のアクションは、すべてゼロの状態を処理するための $U $ として、

$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\ sqrt_ \ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}。
\end{align} $ $

## <a name="input"></a>入力

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

指定された状態を準備するときに使用する近似の許容範囲。


### <a name="coefficients--complexpolar"></a>係数: [Complexpolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]

絶対値とフェーズ $ (r_j、t_j) $ で表される、最大 $ 2 ^ n $ の複合係数の配列。 $J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

リトルエンディアン形式での qubit レジスタのエンコード番号の状態。 この値は、コンピューティングベースの状態 $ \ket{0...0} $ で初期化されることが想定されています。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

負の入力係数 $r _j < $0 は、値 $ | r_j | $ を持つ正の値として処理されます。 `coefficients` $ 2 ^ n $ 未満の場合は、要素 $ (r_j、t_j) = (0.0, 0.0) $ が埋め込まれます。

## <a name="references"></a>リファレンス

- クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176