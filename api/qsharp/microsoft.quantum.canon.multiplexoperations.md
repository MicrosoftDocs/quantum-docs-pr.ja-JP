---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad66b39fcfacbe5231ec3b9ba96989d6d5d449c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206104"
---
# <a name="multiplexoperations-operation"></a>MultiplexOperations 操作

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


数値の状態の配列によって制御される操作の配列を適用します。

つまり、$n $-qubit 数値の状態 $ \ket{j} $ によって制御されている場合は、_j $ の $V によって $ に適用される、多重制御された $U $ に適用されます。

$U = \ sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $。

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="unitaries--t--unit--is-adj--ctl"></a>unitaries: t => [単位](xref:microsoft.quantum.lang-ref.unit)  は形容詞 + Ctl []

最大 $ 2 ^ n $ のユニタリ操作の配列。 $J $ th 操作は、リトルエンディアン形式でエンコードされた数値の状態 $ \ket{j} $ によってインデックスが付けられます。


### <a name="index--littleendian"></a>index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

数値の状態をリトルエンディアン形式でエンコードする $-qubit コントロールレジスタ $n ます。


### <a name="target--t"></a>ターゲット: \

_J $ act に $V する汎用 qubit レジスタ。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&



## <a name="remarks"></a>解説

`coefficients` $ 2 ^ n $ 未満の値が指定されている場合、id 要素が埋め込まれます。 この実装では、$n-$1 補助 qubits を使用します。

## <a name="references"></a>リファレンス

- クォンタムの速度を Childs、Dmitri Maslov、Yunseong、Neil、Ross、人民 Su を使用して最初のクォンタムシミュレーションに向けて https://arxiv.org/abs/1711.10980