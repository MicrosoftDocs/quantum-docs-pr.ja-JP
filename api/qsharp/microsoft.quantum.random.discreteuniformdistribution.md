---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193014"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="3e11c-102">DiscreteUniformDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="3e11c-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="3e11c-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3e11c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3e11c-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="3e11c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3e11c-105">指定された包括範囲に対する一様分布を返します。</span><span class="sxs-lookup"><span data-stu-id="3e11c-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="3e11c-106">入力</span><span class="sxs-lookup"><span data-stu-id="3e11c-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="3e11c-107">最小値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e11c-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e11c-108">描画される最小の整数。</span><span class="sxs-lookup"><span data-stu-id="3e11c-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="3e11c-109">最大値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3e11c-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3e11c-110">描画される最大の整数。</span><span class="sxs-lookup"><span data-stu-id="3e11c-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="3e11c-111">出力: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="3e11c-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="3e11c-112">ランダムな可変性の範囲の整数である分布は、からまでの範囲内の整数です `min` `max` 。</span><span class="sxs-lookup"><span data-stu-id="3e11c-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e11c-113">解説</span><span class="sxs-lookup"><span data-stu-id="3e11c-113">Remarks</span></span>

<span data-ttu-id="3e11c-114">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="3e11c-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e11c-115">参照</span><span class="sxs-lookup"><span data-stu-id="3e11c-115">See Also</span></span>

- [<span data-ttu-id="3e11c-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="3e11c-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)