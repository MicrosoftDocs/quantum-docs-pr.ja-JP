---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193014"
---
# <a name="discreteuniformdistribution-function"></a>DiscreteUniformDistribution 関数

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された包括範囲に対する一様分布を返します。

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a>入力

### <a name="min--int"></a>最小値: [Int](xref:microsoft.quantum.lang-ref.int)

描画される最小の整数。


### <a name="max--int"></a>最大値: [Int](xref:microsoft.quantum.lang-ref.int)

描画される最大の整数。



## <a name="output--discretedistribution"></a>出力: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

ランダムな可変性の範囲の整数である分布は、からまでの範囲内の整数です `min` `max` 。

## <a name="remarks"></a>解説

の場合は失敗し `max <= min` ます。

## <a name="see-also"></a>参照

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)