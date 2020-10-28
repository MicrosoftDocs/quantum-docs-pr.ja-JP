---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709429"
---
# <a name="continuousuniformdistribution-function"></a>ContinuousUniformDistribution 関数

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

パック [](https://nuget.org/packages/)


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

## <a name="remarks"></a>解説

の場合は失敗し `max <= min` ます。

## <a name="see-also"></a>参照

- [DrawRandomDouble](xref:Microsoft.Quantum.DrawRandomDouble)