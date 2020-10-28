---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: 842e7ded1e38f4f6e01e79d2758e30afb85dd349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721274"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


この操作では、qubits のレジスタによって表される整数がもう1つの整数より大きいかどうかをテストして、結果の XOR を出力 qubits に適用します。

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit
```


## <a name="description"></a>説明

2つの整数が指定され、 `x` `y` 同じサイズの qubit レジスタに格納されている場合、この操作は、が満たされているかどうかを確認し `x > y` ます。 True の場合、1は出力 qubit に Xor ます。 それ以外の場合、0は出力 qubit に Xor されます。
言い換えると、この操作は、ユニタリ $ $ \begin{align} U\ket {x} \ k {y} \ k {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)} で表すことができます。
\end{align} $ $

## <a name="input"></a>入力

### <a name="x--littleendian"></a>x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit レジスタの形式で格納されている、比較対象の最初の数値 `LittleEndian` 。


### <a name="y--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit レジスタの形式で格納されている比較対象の2番目の数値 `LittleEndian` 。


### <a name="output--qubit"></a>出力: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

比較 $x>y $ の結果を格納する qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>関連項目

- 新しいクォンタム ripple、Cuccaro、Draper、Samuel、Kutin、David Petrie を追加していますので、 https://arxiv.org/abs/quant-ph/0410184