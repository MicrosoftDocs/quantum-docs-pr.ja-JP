---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 019161c0ef6cdec6875518ab58c8159b0f142149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211748"
---
# <a name="inputencoder-function"></a>InputEncoder 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


係数と許容範囲を指定すると、は、各係数を計算ベース状態の対応する振幅として準備する状態準備操作を返します。

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>入力

### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

入力状態にエンコードされる係数。



## <a name="output--stategenerator"></a>出力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

指定された係数を特定のレジスタの入力状態として準備する状態準備操作。