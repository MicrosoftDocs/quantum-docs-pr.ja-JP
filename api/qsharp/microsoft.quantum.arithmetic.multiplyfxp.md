---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: 乗数 Yfxp 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719779"
---
# <a name="multiplyfxp-operation"></a>乗数 Yfxp 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


クォンタムレジスタの2つの固定小数点数を乗算します。

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>入力

### <a name="fp1--fixedpoint"></a>fp1: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

最初の固定小数点数。


### <a name="fp2--fixedpoint"></a>fp2: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

2番目の固定小数点数。


### <a name="result--fixedpoint"></a>結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

結果の固定小数点数は、初期状態で $ \ket $ である必要があり {0} ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>解説

現在の実装では、3つの固定小数点数が同じポイント位置と同じ数の qubits を持つ必要があります。