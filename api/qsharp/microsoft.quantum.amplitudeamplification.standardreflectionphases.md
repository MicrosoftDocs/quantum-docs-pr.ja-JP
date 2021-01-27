---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardReflectionPhases
title: StandardReflectionPhases 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardReflectionPhases
qsharp.summary: Computes partial reflection phases for standard amplitude amplification.
ms.openlocfilehash: 703b50d0186cd0f4eddb9a29fa3cffb2b746c8d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843913"
---
# <a name="standardreflectionphases-function"></a>StandardReflectionPhases 関数

名前空間: [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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