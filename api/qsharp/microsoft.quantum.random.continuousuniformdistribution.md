---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842315"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution 関数

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


指定された範囲内の一様分布を返します。

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a>入力

### <a name="min--double"></a>最小: [Double](xref:microsoft.quantum.lang-ref.double)

描画される最小の実数。


### <a name="max--double"></a>最大: [Double](xref:microsoft.quantum.lang-ref.double)

描画される最大の実数。



## <a name="output--continuousdistribution"></a>出力: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)

ランダムな可変数を持つ分布は、からまでの範囲内の実数で `min` `max` あり、一様確率を持ちます。

## <a name="example"></a>例

次の Q # スニペットでは、$0 $ と $2 の間の角度をランダムに描画します。

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a>解説

の場合は失敗し `max <= min` ます。

## <a name="see-also"></a>参照

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)