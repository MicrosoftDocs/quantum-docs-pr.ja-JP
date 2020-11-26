---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: a3911fe9962ce18daa239de0272c53d83344134a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193082"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="6ac9b-102">ContinuousUniformDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="6ac9b-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="6ac9b-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6ac9b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6ac9b-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="6ac9b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6ac9b-105">指定された範囲内の一様分布を返します。</span><span class="sxs-lookup"><span data-stu-id="6ac9b-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="6ac9b-106">入力</span><span class="sxs-lookup"><span data-stu-id="6ac9b-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="6ac9b-107">最小: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ac9b-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6ac9b-108">描画される最小の実数。</span><span class="sxs-lookup"><span data-stu-id="6ac9b-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="6ac9b-109">最大: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ac9b-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6ac9b-110">描画される最大の実数。</span><span class="sxs-lookup"><span data-stu-id="6ac9b-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="6ac9b-111">出力: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="6ac9b-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="6ac9b-112">ランダムな可変数を持つ分布は、からまでの範囲内の実数で `min` `max` あり、一様確率を持ちます。</span><span class="sxs-lookup"><span data-stu-id="6ac9b-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ac9b-113">解説</span><span class="sxs-lookup"><span data-stu-id="6ac9b-113">Remarks</span></span>

<span data-ttu-id="6ac9b-114">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="6ac9b-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ac9b-115">参照</span><span class="sxs-lookup"><span data-stu-id="6ac9b-115">See Also</span></span>

- [<span data-ttu-id="6ac9b-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="6ac9b-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)