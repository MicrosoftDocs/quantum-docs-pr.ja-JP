---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723988"
---
# <a name="drawrandomdouble-operation"></a>DrawRandomDouble 操作

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

パック [](https://nuget.org/packages/)


指定した包括間隔でランダムな実数を描画します。

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a>入力

### <a name="min--double"></a>最小: [Double](xref:microsoft.quantum.lang-ref.double)

描画される最小の実数。


### <a name="max--double"></a>最大: [Double](xref:microsoft.quantum.lang-ref.double)

描画される最大の実数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

からまでの範囲内で、 `min` `max` 一様確率を持つランダム実数。

## <a name="remarks"></a>解説

の場合は失敗し `max <= min` ます。

## <a name="see-also"></a>参照

- [ContinuousUniformDistribution](xref:Microsoft.Quantum.ContinuousUniformDistribution)