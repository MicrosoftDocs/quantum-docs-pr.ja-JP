---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724660"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="a386c-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="a386c-102">DrawRandomInt operation</span></span>

<span data-ttu-id="a386c-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a386c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a386c-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a386c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a386c-105">指定した包括範囲内にランダムな整数を描画します。</span><span class="sxs-lookup"><span data-stu-id="a386c-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="a386c-106">入力</span><span class="sxs-lookup"><span data-stu-id="a386c-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="a386c-107">最小値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a386c-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a386c-108">描画される最小の整数。</span><span class="sxs-lookup"><span data-stu-id="a386c-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="a386c-109">最大値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a386c-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a386c-110">描画される最大の整数。</span><span class="sxs-lookup"><span data-stu-id="a386c-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="a386c-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a386c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a386c-112">からまでの範囲に含まれる `min` 、 `max` 一様確率を含む整数。</span><span class="sxs-lookup"><span data-stu-id="a386c-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="a386c-113">解説</span><span class="sxs-lookup"><span data-stu-id="a386c-113">Remarks</span></span>

<span data-ttu-id="a386c-114">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="a386c-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a386c-115">参照</span><span class="sxs-lookup"><span data-stu-id="a386c-115">See Also</span></span>

- [<span data-ttu-id="a386c-116">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="a386c-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)