---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 0a05b8a5891977a08ee2ae6a996657c6a8f3d792
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217120"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a>ApproximatelyApplyDiagonalUnitary 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


複雑なフェーズの配列を、qubits のレジスタの数値ベースの状態に適用し、指定された許容範囲に従って小さな回転角度を切り捨てます。

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

この操作では、$n $ qubit number $ \ket{j} $ に $e ^ {i \ theta_j} $ という複雑なフェーズを適用する斜線を実装します。
特に、この操作は、ユニタリで表すことができます。

$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.
\end{align} $ $

## <a name="input"></a>入力

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

小さい係数が切り捨てられる公差。


### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。 $J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。


### <a name="qubits--littleendian"></a>qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。

## <a name="references"></a>リファレンス

- クォンタムロジック回線の合成、Shende、Stephen、Igor、igor または Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>参照

- [Microsoft. ApplyDiagonalUnitary](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)