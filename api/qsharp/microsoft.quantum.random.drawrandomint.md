---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192912"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="cab95-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="cab95-102">DrawRandomInt operation</span></span>

<span data-ttu-id="cab95-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cab95-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cab95-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="cab95-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cab95-105">指定した包括範囲内にランダムな整数を描画します。</span><span class="sxs-lookup"><span data-stu-id="cab95-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="cab95-106">入力</span><span class="sxs-lookup"><span data-stu-id="cab95-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="cab95-107">最小値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cab95-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cab95-108">描画される最小の整数。</span><span class="sxs-lookup"><span data-stu-id="cab95-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="cab95-109">最大値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cab95-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cab95-110">描画される最大の整数。</span><span class="sxs-lookup"><span data-stu-id="cab95-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="cab95-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cab95-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cab95-112">からまでの範囲に含まれる `min` 、 `max` 一様確率を含む整数。</span><span class="sxs-lookup"><span data-stu-id="cab95-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="cab95-113">解説</span><span class="sxs-lookup"><span data-stu-id="cab95-113">Remarks</span></span>

<span data-ttu-id="cab95-114">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="cab95-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cab95-115">参照</span><span class="sxs-lookup"><span data-stu-id="cab95-115">See Also</span></span>

- [<span data-ttu-id="cab95-116">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="cab95-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)