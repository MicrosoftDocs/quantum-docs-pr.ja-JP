---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723974"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a>SampleTransformedContinuousDistribution 操作

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

パック [](https://nuget.org/packages/)


変換された分布からサンプリングする内部専用操作。
部分的なアプリケーションでのみ使用してください。

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a>入力

### <a name="transform--double---double"></a>変換: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)




### <a name="distribution--continuousdistribution"></a>配布: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)





## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

