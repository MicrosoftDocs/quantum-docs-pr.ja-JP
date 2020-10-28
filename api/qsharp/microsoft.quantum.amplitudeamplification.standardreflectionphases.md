---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: c189b34b641989ab458986fb3f2872759b949be5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721734"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パック [](https://nuget.org/packages/)


標準の振幅増幅の部分的なリフレクションフェーズを計算します。

```qsharp
function StandardReflectionPhases (nIterations : Int) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a>入力

### <a name="niterations--int"></a>nIterations: [Int](xref:microsoft.quantum.lang-ref.int)

部分的なリフレクションフェーズを生成するための振幅増幅の反復回数。



## <a name="output--reflectionphases"></a>出力: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分的な反射として指定されたフェーズを実装する操作

## <a name="remarks"></a>解説

すべてのフェーズは $ \ pi $ ですが、開始状態に関する最初のリフレクションとターゲット状態に関する最後のリフレクション ($0 $) は除きます。