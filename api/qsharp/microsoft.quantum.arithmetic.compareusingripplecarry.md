---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843280"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


この操作では、qubits のレジスタによって表される整数がもう1つの整数より大きいかどうかをテストして、結果の XOR を出力 qubits に適用します。

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
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



## <a name="references"></a>References

- 新しいクォンタム ripple、Cuccaro、Draper、Samuel、Kutin、David Petrie を追加していますので、 https://arxiv.org/abs/quant-ph/0410184