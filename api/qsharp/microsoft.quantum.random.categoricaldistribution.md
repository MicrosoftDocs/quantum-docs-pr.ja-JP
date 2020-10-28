---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722817"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="3b6f5-102">CategoricalDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="3b6f5-102">CategoricalDistribution function</span></span>

<span data-ttu-id="3b6f5-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3b6f5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3b6f5-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b6f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b6f5-105">個別のカテゴリ分布を返します。この分布では、特定の結果の有限のリストの各確率が明示的に指定されます。</span><span class="sxs-lookup"><span data-stu-id="3b6f5-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="3b6f5-106">入力</span><span class="sxs-lookup"><span data-stu-id="3b6f5-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="3b6f5-107">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3b6f5-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3b6f5-108">カテゴリ分布の各結果の確率。</span><span class="sxs-lookup"><span data-stu-id="3b6f5-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="3b6f5-109">これらの確率は正規化されない可能性がありますが、すべてが負でない値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b6f5-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="3b6f5-110">出力: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="3b6f5-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="3b6f5-111">`i`確率を持つインデックス `probs[i] / sum` 。ここ `sum` で、は `probs` によって指定されたの合計です `Fold(PlusD, 0.0, probs)` 。</span><span class="sxs-lookup"><span data-stu-id="3b6f5-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>