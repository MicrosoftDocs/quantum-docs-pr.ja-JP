---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721135"
---
# <a name="greaterthan-operation"></a>GreaterThan 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


Qubit レジスタにエンコードされた2つの整数の間で、比較の結果に基づいてターゲットの qubit を反転させることにより、より大きい比較を適用します。

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a>説明

は、qubit レジスタ xs および y でエンコードされた、$ および $y $ $x 2 つの整数の比較を厳密に上回る比較を実行します。 $X > y $ の場合は、結果の qubit が反転されます。それ以外の場合、結果の qubit はその状態を保持します。

## <a name="input"></a>入力

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit レジスタは、$ $x 最初の整数をエンコードします。


### <a name="ys--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit レジスタでは、2番目の整数 $y $ としてエンコードされます。


### <a name="result--qubit"></a>結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Y $ $x > 場合に反転される単一の qubit。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

は、-y = (x ' + y) ' $ の $x を使用します。ここで、' は1の補数を表します。

## <a name="references"></a>関連項目

- Cuccaro、Draper、Samuel、Kutin、David Petrie の: "新しいクォンタム ripple-キャリー追加回路", 2004 ですが、このようになります。
  https://arxiv.org/abs/quant-ph/0410184v1

- トーマス Haener、Martin Roetteler、Krysta: "2n + 2 qubits と Toffoli ベースのモジュール乗算を使用したファクタリング"、2016 https://arxiv.org/abs/1611.07995