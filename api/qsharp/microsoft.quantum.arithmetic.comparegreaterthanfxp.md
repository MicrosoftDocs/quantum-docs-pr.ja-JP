---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721298"
---
# <a name="comparegreaterthanfxp-operation"></a>CompareGreaterThanFxP 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


クォンタムレジスタに格納されている2つの固定小数点数を比較し、結果のフリップを制御します。

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a>入力

### <a name="fp1--fixedpoint"></a>fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

比較する最初の固定小数点数。


### <a name="fp2--fixedpoint"></a>fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

比較する2番目の固定小数点数。


### <a name="result--qubit"></a>結果: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

比較の結果。 は、の場合には反転され `fp1 > fp2` ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

現在の実装では、2つの固定小数点数が同じポイント位置と同じ数の qubits を持つ必要があります。