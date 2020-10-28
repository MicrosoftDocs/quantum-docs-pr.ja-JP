---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721195"
---
# <a name="evaluateoddpolynomialfxp-operation"></a>EvaluateOddPolynomialFxP 操作

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


固定小数点表現で奇数の多項式を評価します。

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>入力

### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

奇数多項式の係数 (配列 $ [a_0, a_1,..., a_k] $、奇数多項式の $P (x) = a_0 x + a_1 x ^ 3 + \ cドット + a_k x ^ {2k + 1} $) の2つの配列。


### <a name="fpx--fixedpoint"></a>fpx: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

多項式を評価する固定小数点数を入力します。


### <a name="result--fixedpoint"></a>結果: [Fixedpoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

P (x) を保持する固定小数点数を出力します。 最初は、状態が $ \ket $ である必要があり {0} ます。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

