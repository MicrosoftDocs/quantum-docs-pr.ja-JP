---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856124"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="85d9d-102">MaybeChooseElement 操作</span><span class="sxs-lookup"><span data-stu-id="85d9d-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="85d9d-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="85d9d-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="85d9d-104">Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア</span><span class="sxs-lookup"><span data-stu-id="85d9d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="85d9d-105">データの配列とそのインデックスに対する分布を指定すると、はランダムに要素を選択しようとします。</span><span class="sxs-lookup"><span data-stu-id="85d9d-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="85d9d-106">入力</span><span class="sxs-lookup"><span data-stu-id="85d9d-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="85d9d-107">データ: ' t []</span><span class="sxs-lookup"><span data-stu-id="85d9d-107">data : 'T[]</span></span>

<span data-ttu-id="85d9d-108">要素を選択する配列。</span><span class="sxs-lookup"><span data-stu-id="85d9d-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="85d9d-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="85d9d-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="85d9d-110">のインデックスに対する分布 `data` 。</span><span class="sxs-lookup"><span data-stu-id="85d9d-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="85d9d-111">出力: ([Bool](xref:microsoft.quantum.lang-ref.bool), t)</span><span class="sxs-lookup"><span data-stu-id="85d9d-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="85d9d-112">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="85d9d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85d9d-113">&</span><span class="sxs-lookup"><span data-stu-id="85d9d-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="85d9d-114">例</span><span class="sxs-lookup"><span data-stu-id="85d9d-114">Example</span></span>

<span data-ttu-id="85d9d-115">次の Q # スニペットは、配列からランダムに要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="85d9d-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```