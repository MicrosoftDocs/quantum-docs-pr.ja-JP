---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 1fc8a8857b6b37d4c3e812a3c4cb2941b9238800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844572"
---
# <a name="approximatelymultiplexpauli-operation"></a>ApproximatelyMultiplexPauli 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Qubits の配列で条件付きの回転を適用し、指定された許容範囲に従って小さな回転角度を切り捨てます。

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

これは、$n $ qubit number $ \ket{j} $ によって制御されている場合に、single qubit p Li operator $P $ の角度 $ \ theta_j $ によって回転を実行する、多重制御された、乗算操作を適用します。
特に、この操作のアクションは、ユニタリによって表されます。

$ $ \begin{align} U = \ sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}/otimes e ^ {i P \ theta_j}。
\end{align}

##

## <a name="input"></a>入力

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

小さい係数が切り捨てられる公差。


### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

$ 2 ^ n $ 係数 $ \ theta_j $ までの配列。 $J $ th 係数は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ にインデックスを付けます。


### <a name="pauli--pauli"></a>p# li: [p#](xref:microsoft.quantum.lang-ref.pauli) li

回転の軸を決定する p$P li 演算子。


### <a name="control--littleendian"></a>control: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。


### <a name="target--qubit"></a>ターゲット: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

$E ^ {i P \ theta_j} $ によって回転された1つの qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

`coefficients` $ 2 ^ n $ 未満の値が指定されている場合は、$ \ theta_j = $0.0 という要素が埋め込まれます。

## <a name="see-also"></a>参照

- [Microsoft. Canon....](xref:Microsoft.Quantum.Canon.MultiplexPauli)