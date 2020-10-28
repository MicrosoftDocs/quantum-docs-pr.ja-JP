---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724660"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt 操作

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

パック [](https://nuget.org/packages/)


指定した包括範囲内にランダムな整数を描画します。

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a>入力

### <a name="min--int"></a>最小値: [Int](xref:microsoft.quantum.lang-ref.int)

描画される最小の整数。


### <a name="max--int"></a>最大値: [Int](xref:microsoft.quantum.lang-ref.int)

描画される最大の整数。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

からまでの範囲に含まれる `min` 、 `max` 一様確率を含む整数。

## <a name="remarks"></a>解説

の場合は失敗し `max <= min` ます。

## <a name="see-also"></a>参照

- [DiscreteUniformDistribution](xref:Microsoft.Quantum.DiscreteUniformDistribution)