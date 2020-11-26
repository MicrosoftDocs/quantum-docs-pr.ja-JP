---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 2e3d9b17939d5a9a5bc5e7d89a843e0ff5a848ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210252"
---
# <a name="categoricaldistribution-function"></a>CategoricalDistribution 関数

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


個別のカテゴリ分布を返します。この分布では、特定の結果の有限のリストの各確率が明示的に指定されます。

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>入力

### <a name="probs--double"></a>probs: [Double](xref:microsoft.quantum.lang-ref.double)[]

カテゴリ分布の各結果の確率。
これらの確率は正規化されない可能性がありますが、すべてが負でない値である必要があります。



## <a name="output--discretedistribution"></a>出力: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

`i`確率を持つインデックス `probs[i] / sum` 。ここ `sum` で、は `probs` によって指定されたの合計です `Fold(PlusD, 0.0, probs)` 。