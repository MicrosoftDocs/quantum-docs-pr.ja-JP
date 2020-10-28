---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 6c0558ded2bd018afad84c42c2d15fc029ac0d44
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723988"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="3f559-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="3f559-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="3f559-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3f559-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3f559-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3f559-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3f559-105">指定した包括間隔でランダムな実数を描画します。</span><span class="sxs-lookup"><span data-stu-id="3f559-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="3f559-106">入力</span><span class="sxs-lookup"><span data-stu-id="3f559-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="3f559-107">最小: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f559-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f559-108">描画される最小の実数。</span><span class="sxs-lookup"><span data-stu-id="3f559-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="3f559-109">最大: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f559-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f559-110">描画される最大の実数。</span><span class="sxs-lookup"><span data-stu-id="3f559-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="3f559-111">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3f559-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3f559-112">からまでの範囲内で、 `min` `max` 一様確率を持つランダム実数。</span><span class="sxs-lookup"><span data-stu-id="3f559-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f559-113">解説</span><span class="sxs-lookup"><span data-stu-id="3f559-113">Remarks</span></span>

<span data-ttu-id="3f559-114">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="3f559-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f559-115">参照</span><span class="sxs-lookup"><span data-stu-id="3f559-115">See Also</span></span>

- [<span data-ttu-id="3f559-116">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="3f559-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)