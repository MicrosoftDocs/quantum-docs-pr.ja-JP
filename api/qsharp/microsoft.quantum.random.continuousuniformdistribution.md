---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842315"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="fa4d4-102">ContinuousUniformDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="fa4d4-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="fa4d4-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="fa4d4-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="fa4d4-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="fa4d4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fa4d4-105">指定された範囲内の一様分布を返します。</span><span class="sxs-lookup"><span data-stu-id="fa4d4-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="fa4d4-106">入力</span><span class="sxs-lookup"><span data-stu-id="fa4d4-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="fa4d4-107">最小: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa4d4-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fa4d4-108">描画される最小の実数。</span><span class="sxs-lookup"><span data-stu-id="fa4d4-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="fa4d4-109">最大: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa4d4-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="fa4d4-110">描画される最大の実数。</span><span class="sxs-lookup"><span data-stu-id="fa4d4-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="fa4d4-111">出力: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="fa4d4-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="fa4d4-112">ランダムな可変数を持つ分布は、からまでの範囲内の実数で `min` `max` あり、一様確率を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fa4d4-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="fa4d4-113">例</span><span class="sxs-lookup"><span data-stu-id="fa4d4-113">Example</span></span>

<span data-ttu-id="fa4d4-114">次の Q # スニペットでは、$0 $ と $2 の間の角度をランダムに描画します。</span><span class="sxs-lookup"><span data-stu-id="fa4d4-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="fa4d4-115">解説</span><span class="sxs-lookup"><span data-stu-id="fa4d4-115">Remarks</span></span>

<span data-ttu-id="fa4d4-116">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="fa4d4-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa4d4-117">参照</span><span class="sxs-lookup"><span data-stu-id="fa4d4-117">See Also</span></span>

- [<span data-ttu-id="fa4d4-118">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="fa4d4-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)