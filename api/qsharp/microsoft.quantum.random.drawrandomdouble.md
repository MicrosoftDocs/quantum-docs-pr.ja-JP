---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192946"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="7b854-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="7b854-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="7b854-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="7b854-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="7b854-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="7b854-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="7b854-105">指定した包括間隔でランダムな実数を描画します。</span><span class="sxs-lookup"><span data-stu-id="7b854-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="7b854-106">入力</span><span class="sxs-lookup"><span data-stu-id="7b854-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="7b854-107">最小: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7b854-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7b854-108">描画される最小の実数。</span><span class="sxs-lookup"><span data-stu-id="7b854-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="7b854-109">最大: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7b854-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7b854-110">描画される最大の実数。</span><span class="sxs-lookup"><span data-stu-id="7b854-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="7b854-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7b854-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7b854-112">からまでの範囲内で、 `min` `max` 一様確率を持つランダム実数。</span><span class="sxs-lookup"><span data-stu-id="7b854-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="7b854-113">解説</span><span class="sxs-lookup"><span data-stu-id="7b854-113">Remarks</span></span>

<span data-ttu-id="7b854-114">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="7b854-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b854-115">参照</span><span class="sxs-lookup"><span data-stu-id="7b854-115">See Also</span></span>

- [<span data-ttu-id="7b854-116">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="7b854-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)