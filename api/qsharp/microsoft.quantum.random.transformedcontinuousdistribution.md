---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226266"
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