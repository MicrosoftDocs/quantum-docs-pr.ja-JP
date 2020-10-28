---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720283"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="58b75-102">DrawCategorical 操作</span><span class="sxs-lookup"><span data-stu-id="58b75-102">DrawCategorical operation</span></span>

<span data-ttu-id="58b75-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="58b75-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="58b75-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58b75-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58b75-105">Probablities のリストによって指定されたカテゴリ分布からランダムサンプルを描画します。</span><span class="sxs-lookup"><span data-stu-id="58b75-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="58b75-106">説明</span><span class="sxs-lookup"><span data-stu-id="58b75-106">Description</span></span>

<span data-ttu-id="58b75-107">特定のインデックスを選択する確率は、そのインデックス位置にある配列要素の値に比例します。</span><span class="sxs-lookup"><span data-stu-id="58b75-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="58b75-108">0に等しい配列要素は無視され、インデックスは返されません。</span><span class="sxs-lookup"><span data-stu-id="58b75-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="58b75-109">配列要素が0未満の場合、または配列要素がゼロより大きい場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="58b75-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="58b75-110">入力</span><span class="sxs-lookup"><span data-stu-id="58b75-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="58b75-111">probs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="58b75-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="58b75-112">各インデックスを選択する確率に比例した浮動小数点数の配列。</span><span class="sxs-lookup"><span data-stu-id="58b75-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="58b75-113">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="58b75-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="58b75-114">確率が $ \ Pr (i) = p_i/\ sum_i p_i $ の整数 $i $。ここで $p _i $ は、の $i $ th 要素 `probs` です。</span><span class="sxs-lookup"><span data-stu-id="58b75-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="58b75-115">参照</span><span class="sxs-lookup"><span data-stu-id="58b75-115">See Also</span></span>

- [<span data-ttu-id="58b75-116">CategoricalDistribution の場合</span><span class="sxs-lookup"><span data-stu-id="58b75-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)