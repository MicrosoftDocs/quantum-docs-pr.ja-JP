---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192861"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="862d3-102">MaybeChooseElement 操作</span><span class="sxs-lookup"><span data-stu-id="862d3-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="862d3-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="862d3-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="862d3-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="862d3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="862d3-105">データの配列とそのインデックスに対する分布を指定すると、はランダムに要素を選択しようとします。</span><span class="sxs-lookup"><span data-stu-id="862d3-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="862d3-106">入力</span><span class="sxs-lookup"><span data-stu-id="862d3-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="862d3-107">データ: ' t []</span><span class="sxs-lookup"><span data-stu-id="862d3-107">data : 'T[]</span></span>

<span data-ttu-id="862d3-108">要素を選択する配列。</span><span class="sxs-lookup"><span data-stu-id="862d3-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="862d3-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="862d3-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="862d3-110">のインデックスに対する分布 `data` 。</span><span class="sxs-lookup"><span data-stu-id="862d3-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="862d3-111">出力: ([Bool](xref:microsoft.quantum.lang-ref.bool), t)</span><span class="sxs-lookup"><span data-stu-id="862d3-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="862d3-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="862d3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="862d3-113">&</span><span class="sxs-lookup"><span data-stu-id="862d3-113">'T</span></span>

