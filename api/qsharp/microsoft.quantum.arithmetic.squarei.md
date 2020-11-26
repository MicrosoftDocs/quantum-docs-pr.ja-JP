---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221863"
---
# <a name="squarei-operation"></a>SquareI 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パッケージ: [Microsoft. Quantum. 数値](https://nuget.org/packages/Microsoft.Quantum.Numerics)


整数の2乗をに計算し `xs` `result` ます。最初はゼロである必要があります。

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>入力

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ ビットの数値を平方根 (LittleEndian)


### <a name="result--littleendian"></a>結果: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ 2n $ ビット結果 (LittleEndian) は、初期状態で $ \ket $ である必要があり {0} ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

は、標準的なシフトアンド追加アプローチを使用して、正方形を計算します。 は、通常の乗数を適用してコピー操作を元に戻す前に、最初に xs をコピーする、ストレート転送ソリューションと比較して $n-$1 qubits を保存します。