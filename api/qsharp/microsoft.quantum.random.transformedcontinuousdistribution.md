---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857768"
---
# <a name="transformedcontinuousdistribution-function"></a>TransformedContinuousDistribution 関数

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


連続分布の場合は、指定された関数によって元のを変換する新しい分布を返します。

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>入力

### <a name="transform--double---double"></a>変換: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)

元の分布の可変数を変換された分布に変換する関数。


### <a name="distribution--continuousdistribution"></a>配布: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

変換する元の分布。



## <a name="output--continuousdistribution"></a>出力: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

によって指定された変換によってに関連する新しい分布 `distribution` `transform` 。

## <a name="example"></a>例

次の2つのディストリビューションは同じです。

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```