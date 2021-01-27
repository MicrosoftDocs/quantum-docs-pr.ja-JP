---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847627"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="eca00-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="eca00-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="eca00-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="eca00-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="eca00-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="eca00-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="eca00-105">指定した包括間隔でランダムな実数を描画します。</span><span class="sxs-lookup"><span data-stu-id="eca00-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="eca00-106">入力</span><span class="sxs-lookup"><span data-stu-id="eca00-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="eca00-107">最小: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eca00-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eca00-108">描画される最小の実数。</span><span class="sxs-lookup"><span data-stu-id="eca00-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="eca00-109">最大: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eca00-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eca00-110">描画される最大の実数。</span><span class="sxs-lookup"><span data-stu-id="eca00-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="eca00-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="eca00-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="eca00-112">からまでの範囲内で、 `min` `max` 一様確率を持つランダム実数。</span><span class="sxs-lookup"><span data-stu-id="eca00-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="eca00-113">例</span><span class="sxs-lookup"><span data-stu-id="eca00-113">Example</span></span>

<span data-ttu-id="eca00-114">次の Q # スニペットでは、$0 $ と $2 の間の角度をランダムに描画します。</span><span class="sxs-lookup"><span data-stu-id="eca00-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="eca00-115">解説</span><span class="sxs-lookup"><span data-stu-id="eca00-115">Remarks</span></span>

<span data-ttu-id="eca00-116">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="eca00-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="eca00-117">参照</span><span class="sxs-lookup"><span data-stu-id="eca00-117">See Also</span></span>

- [<span data-ttu-id="eca00-118">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="eca00-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)