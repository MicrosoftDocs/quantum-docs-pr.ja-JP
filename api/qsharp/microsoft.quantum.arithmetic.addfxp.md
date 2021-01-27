---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 60b7cad3d0bd8800e67830ca921f8e2d705b8f39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843872"
---
# <a name="addfxp-operation"></a>AddFxP 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)


クォンタムレジスタに格納されている2つの固定小数点数を追加します。

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a>説明

それぞれ、州 $ \ket{f_1} $ および $ \ket{f_2} $ に2つの固定小数点レジスタが指定されている場合、操作 $ \ket{f_1} \ket{f_2} \ map\ket{f_1} \ket{f_1 + f_2} $ が実行されます。

## <a name="input"></a>入力

### <a name="fp1--fixedpoint"></a>fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

最初の固定小数点数


### <a name="fp2--fixedpoint"></a>fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

2番目の固定小数点数は、2つの入力の合計を含むように更新されます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

現在の実装では、2つの固定小数点数が、最下位ビットから同じポイント位置を持つ必要があります。つまり、$n _i $ と $p _i は同じである必要があります。