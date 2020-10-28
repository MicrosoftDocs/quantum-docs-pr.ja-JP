---
uid: Microsoft.Quantum.Random.BigDiscreteDistribution
title: BigDiscreteDistribution ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: BigDiscreteDistribution
qsharp.summary: Represents a univariate probability distribution over integers of arbitrary size.
ms.openlocfilehash: d3aba17c8bb4d49f09279b6910e0e56a8e20a6d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722854"
---
# <a name="bigdiscretedistribution-user-defined-type"></a>BigDiscreteDistribution ユーザー定義型

名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

パック [](https://nuget.org/packages/)


任意のサイズの整数に対する uni可変分布確率分布を表します。

```qsharp

newtype BigDiscreteDistribution = (Sample : (Unit => BigInt));
```



## <a name="named-items"></a>名前付き項目

### <a name="sample--unit--bigint"></a>サンプル: [Unit](xref:microsoft.quantum.lang-ref.unit) => [BigInt](xref:microsoft.quantum.lang-ref.bigint) 



## <a name="see-also"></a>参照

- [ContinuousDistribution の場合](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [Microsoft Quantum の ComplexDistribution](xref:Microsoft.Quantum.Random.ComplexDistribution)
- [DiscreteDistribution の場合](xref:Microsoft.Quantum.Random.DiscreteDistribution)