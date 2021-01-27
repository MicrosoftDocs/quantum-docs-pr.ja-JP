---
uid: Microsoft.Quantum.Random.StandardNormalDistribution
title: StandardNormalDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: StandardNormalDistribution
qsharp.summary: Returns a normal distribution with mean 0 and variance 1.
ms.openlocfilehash: e1776339655c33516f7b3d156f1b377a0c74d250
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857807"
---
# <a name="standardnormaldistribution-function"></a>StandardNormalDistribution 関数

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


平均0および分散1を持つ正規分布を返します。

```qsharp
function StandardNormalDistribution () : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="output--continuousdistribution"></a>出力: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)



## <a name="example"></a>例

次の例では、標準正規分布から10個のサンプルを描画します。

```qsharp
let samples = DrawMany((StandardNormalDistribution())::Sample, 10, ());
```

## <a name="see-also"></a>参照

- ["Microsoft..................](xref:Microsoft.Quantum.Random.NormalDistribution)