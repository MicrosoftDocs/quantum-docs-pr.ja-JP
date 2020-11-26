---
uid: Microsoft.Quantum.MachineLearning.ApproximateInputEncoder
title: ApproximateInputEncoder 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ApproximateInputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state, up to the given tolerance.
ms.openlocfilehash: 2e39318cfaf3321c33b08f742bb25a9276b7e660
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196601"
---
# <a name="approximateinputencoder-function"></a>ApproximateInputEncoder 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


係数と許容範囲が指定されている場合、は、指定された許容範囲に対して、計算ベース状態の対応する振幅として各係数を準備する状態準備操作を返します。

```qsharp
function ApproximateInputEncoder (tolerance : Double, coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>入力

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

指定された係数を入力状態にエンコードするときに使用される近似許容範囲。


### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

入力状態にエンコードされる係数。



## <a name="output--stategenerator"></a>出力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

指定された係数を特定のレジスタの入力状態として準備する状態準備操作。