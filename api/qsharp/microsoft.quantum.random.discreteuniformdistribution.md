---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853717"
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

## <a name="example"></a>例

次の Q # スニペットは、6辺をランダムにロールします。

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a>解説

の場合は失敗し `max <= min` ます。

## <a name="see-also"></a>参照

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)