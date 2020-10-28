---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720295"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="f768a-102">DiscreteUniformDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="f768a-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="f768a-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f768a-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f768a-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f768a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f768a-105">指定された包括範囲に対する一様分布を返します。</span><span class="sxs-lookup"><span data-stu-id="f768a-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="f768a-106">入力</span><span class="sxs-lookup"><span data-stu-id="f768a-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="f768a-107">最小値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f768a-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f768a-108">描画される最小の整数。</span><span class="sxs-lookup"><span data-stu-id="f768a-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="f768a-109">最大値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f768a-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f768a-110">描画される最大の整数。</span><span class="sxs-lookup"><span data-stu-id="f768a-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="f768a-111">出力: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="f768a-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="f768a-112">ランダムな可変性の範囲の整数である分布は、からまでの範囲内の整数です `min` `max` 。</span><span class="sxs-lookup"><span data-stu-id="f768a-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="f768a-113">解説</span><span class="sxs-lookup"><span data-stu-id="f768a-113">Remarks</span></span>

<span data-ttu-id="f768a-114">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="f768a-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f768a-115">参照</span><span class="sxs-lookup"><span data-stu-id="f768a-115">See Also</span></span>

- [<span data-ttu-id="f768a-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="f768a-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)