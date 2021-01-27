---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842347"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="3b0db-102">CategoricalDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="3b0db-102">CategoricalDistribution function</span></span>

<span data-ttu-id="3b0db-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3b0db-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3b0db-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="3b0db-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3b0db-105">個別のカテゴリ分布を返します。この分布では、特定の結果の有限のリストの各確率が明示的に指定されます。</span><span class="sxs-lookup"><span data-stu-id="3b0db-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="3b0db-106">入力</span><span class="sxs-lookup"><span data-stu-id="3b0db-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="3b0db-107">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3b0db-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3b0db-108">カテゴリ分布の各結果の確率。</span><span class="sxs-lookup"><span data-stu-id="3b0db-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="3b0db-109">これらの確率は正規化されない可能性がありますが、すべてが負でない値である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b0db-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="3b0db-110">出力: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="3b0db-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="3b0db-111">`i`確率を持つインデックス `probs[i] / sum` 。ここ `sum` で、は `probs` によって指定されたの合計です `Fold(PlusD, 0.0, probs)` 。</span><span class="sxs-lookup"><span data-stu-id="3b0db-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="3b0db-112">例</span><span class="sxs-lookup"><span data-stu-id="3b0db-112">Example</span></span>

<span data-ttu-id="3b0db-113">次の Q # コードでは、確率が30%、1が確率が70% の0が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b0db-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```