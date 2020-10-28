---
uid: Microsoft.Quantum.Random.ComplexDistribution
title: ComplexDistribution ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ComplexDistribution
qsharp.summary: Represents a univariate probability distribution over complex numbers.
ms.openlocfilehash: eb66284694a69d3e14713b067d212cd37d1acab8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722812"
---
# <a name="complexdistribution-user-defined-type"></a>ComplexDistribution ユーザー定義型

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

パック [](https://nuget.org/packages/)


複素数に対する uninumbers の確率分布を表します。

```qsharp

newtype ComplexDistribution = (Sample : (Unit => Microsoft.Quantum.Math.Complex));
```



## <a name="named-items"></a>名前付き項目

### <a name="sample--unit--complex"></a>サンプル: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Complex](xref:Microsoft.Quantum.Math.Complex) 



## <a name="see-also"></a>参照

- [ContinuousDistribution の場合](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [DiscreteDistribution の場合](xref:Microsoft.Quantum.Random.DiscreteDistribution)
- [BigDiscreteDistribution の場合](xref:Microsoft.Quantum.Random.BigDiscreteDistribution)