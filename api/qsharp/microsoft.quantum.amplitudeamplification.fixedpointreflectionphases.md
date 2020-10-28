---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 6ab2a8c6cb0b390f96aa13ece5d5b89c196a6107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721860"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パック [](https://nuget.org/packages/)


固定小数点の振幅増幅の部分的なリフレクションフェーズを計算します。

```qsharp
function FixedPointReflectionPhases (nQueries : Int, successMin : Double) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>入力

### <a name="nqueries--int"></a>nQueries: [Int](xref:microsoft.quantum.lang-ref.int)

状態準備 oracle に対するクエリの数。 は奇数の整数である必要があります。


### <a name="successmin--double"></a>successMin: [Double](xref:microsoft.quantum.lang-ref.double)

ターゲットの最小成功確率。



## <a name="output--reflectionphases"></a>出力: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

固定小数点数の振幅増幅クォンタムアルゴリズムの実装で使用できるフェーズの配列。

## <a name="references"></a>関連項目

「最適な数のクエリを使用した固定ポイントの振幅増幅」のフェーズを使用します。

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 「複合クォンタムゲートの手法」も参照してください。
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) は、の形式のフェーズを `RotationPhases` 指定します。