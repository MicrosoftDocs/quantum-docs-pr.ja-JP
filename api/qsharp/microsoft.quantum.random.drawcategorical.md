---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a9fe1b08e80abc65a5c4b803f0cb8a5e7a62759c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851147"
---
# <a name="drawcategorical-operation"></a>DrawCategorical 操作

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


Probablities のリストによって指定されたカテゴリ分布からランダムサンプルを描画します。

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>説明

特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。
0に等しい配列要素は無視され、インデックスは返されません。 配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。

## <a name="input"></a>入力

### <a name="probs--double"></a>probs: [Double](xref:microsoft.quantum.lang-ref.double)[]

各インデックスを選択する確率に比例した浮動小数点数の配列。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

確率が $ \ Pr (i) = p_i/\ sum_i p_i $ の整数 $i $。ここで $p _i $ は、の $i $ th 要素 `probs` です。

## <a name="see-also"></a>参照

- [CategoricalDistribution の場合](xref:Microsoft.Quantum.Random.CategoricalDistribution)