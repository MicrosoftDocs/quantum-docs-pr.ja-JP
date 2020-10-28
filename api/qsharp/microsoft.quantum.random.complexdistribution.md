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
# <a name="complexdistribution-user-defined-type"></a><span data-ttu-id="65c57-102">ComplexDistribution ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="65c57-102">ComplexDistribution user defined type</span></span>

<span data-ttu-id="65c57-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="65c57-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="65c57-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65c57-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65c57-105">複素数に対する uninumbers の確率分布を表します。</span><span class="sxs-lookup"><span data-stu-id="65c57-105">Represents a univariate probability distribution over complex numbers.</span></span>

```qsharp

newtype ComplexDistribution = (Sample : (Unit => Microsoft.Quantum.Math.Complex));
```



## <a name="named-items"></a><span data-ttu-id="65c57-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="65c57-106">Named Items</span></span>

### <a name="sample--unit--complex"></a><span data-ttu-id="65c57-107">サンプル: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Complex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="65c57-107">Sample : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span> 



## <a name="see-also"></a><span data-ttu-id="65c57-108">参照</span><span class="sxs-lookup"><span data-stu-id="65c57-108">See Also</span></span>

- [<span data-ttu-id="65c57-109">ContinuousDistribution の場合</span><span class="sxs-lookup"><span data-stu-id="65c57-109">Microsoft.Quantum.Random.ContinuousDistribution</span></span>](xref:Microsoft.Quantum.Random.ContinuousDistribution)
- [<span data-ttu-id="65c57-110">DiscreteDistribution の場合</span><span class="sxs-lookup"><span data-stu-id="65c57-110">Microsoft.Quantum.Random.DiscreteDistribution</span></span>](xref:Microsoft.Quantum.Random.DiscreteDistribution)
- [<span data-ttu-id="65c57-111">BigDiscreteDistribution の場合</span><span class="sxs-lookup"><span data-stu-id="65c57-111">Microsoft.Quantum.Random.BigDiscreteDistribution</span></span>](xref:Microsoft.Quantum.Random.BigDiscreteDistribution)