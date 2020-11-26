---
uid: Microsoft.Quantum.AmplitudeAmplification.FixedPointReflectionPhases
title: FixedPointReflectionPhases 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: FixedPointReflectionPhases
qsharp.summary: Computes partial reflection phases for fixed-point amplitude amplification.
ms.openlocfilehash: 8cc1073447f5fae87ece38db64dcc312f6208899
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191450"
---
# <a name="fixedpointreflectionphases-function"></a>FixedPointReflectionPhases 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="references"></a>リファレンス

「最適な数のクエリを使用した固定ポイントの振幅増幅」のフェーズを使用します。

- [YoderLowChuang2014](https://arxiv.org/abs/1409.3305) 「複合クォンタムゲートの手法」も参照してください。
- [LowYoderChuang2016](https://arxiv.org/abs/1603.03996) は、の形式のフェーズを `RotationPhases` 指定します。