---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192912"
---
# <a name="drawrandomint-operation"></a>DrawRandomInt 操作

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


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