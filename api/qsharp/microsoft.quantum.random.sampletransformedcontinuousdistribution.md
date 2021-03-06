---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: 62f6f4ff372143228de007c98a23697022fcfd24
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856101"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a>SampleTransformedContinuousDistribution 操作

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


変換された分布からサンプリングする内部専用操作。
部分的なアプリケーションでのみ使用してください。

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a>入力

### <a name="transform--double---double"></a>変換: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)




### <a name="distribution--continuousdistribution"></a>配布: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)





## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

