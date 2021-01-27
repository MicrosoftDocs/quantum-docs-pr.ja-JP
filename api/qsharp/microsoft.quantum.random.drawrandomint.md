---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: ebed7f52b7c4a8c538ed9d718c486b5aa94a0327
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851138"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="3eca6-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="3eca6-102">DrawRandomInt operation</span></span>

<span data-ttu-id="3eca6-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3eca6-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3eca6-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="3eca6-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3eca6-105">指定した包括範囲内にランダムな整数を描画します。</span><span class="sxs-lookup"><span data-stu-id="3eca6-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="3eca6-106">入力</span><span class="sxs-lookup"><span data-stu-id="3eca6-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="3eca6-107">最小値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3eca6-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3eca6-108">描画される最小の整数。</span><span class="sxs-lookup"><span data-stu-id="3eca6-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="3eca6-109">最大値: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3eca6-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3eca6-110">描画される最大の整数。</span><span class="sxs-lookup"><span data-stu-id="3eca6-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="3eca6-111">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3eca6-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3eca6-112">からまでの範囲に含まれる `min` 、 `max` 一様確率を含む整数。</span><span class="sxs-lookup"><span data-stu-id="3eca6-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="3eca6-113">例</span><span class="sxs-lookup"><span data-stu-id="3eca6-113">Example</span></span>

<span data-ttu-id="3eca6-114">次の Q # スニペットは、6辺をランダムにロールします。</span><span class="sxs-lookup"><span data-stu-id="3eca6-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let roll = DrawRandomInt(1, 6);
```

## <a name="remarks"></a><span data-ttu-id="3eca6-115">解説</span><span class="sxs-lookup"><span data-stu-id="3eca6-115">Remarks</span></span>

<span data-ttu-id="3eca6-116">の場合は失敗し `max <= min` ます。</span><span class="sxs-lookup"><span data-stu-id="3eca6-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3eca6-117">参照</span><span class="sxs-lookup"><span data-stu-id="3eca6-117">See Also</span></span>

- [<span data-ttu-id="3eca6-118">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="3eca6-118">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)