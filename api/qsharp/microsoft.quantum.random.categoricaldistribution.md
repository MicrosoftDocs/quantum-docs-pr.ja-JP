---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842347"
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

## <a name="example"></a>例

次の Q # コードでは、確率が30%、1が確率が70% の0が表示されます。

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```