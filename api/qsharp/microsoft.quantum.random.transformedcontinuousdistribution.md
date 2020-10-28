---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710941"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="b7be0-102">TransformedContinuousDistribution 関数</span><span class="sxs-lookup"><span data-stu-id="b7be0-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="b7be0-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b7be0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b7be0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b7be0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b7be0-105">連続分布の場合は、指定された関数によって元のを変換する新しい分布を返します。</span><span class="sxs-lookup"><span data-stu-id="b7be0-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="b7be0-106">入力</span><span class="sxs-lookup"><span data-stu-id="b7be0-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="b7be0-107">変換: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b7be0-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b7be0-108">元の分布の可変数を変換された分布に変換する関数。</span><span class="sxs-lookup"><span data-stu-id="b7be0-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="b7be0-109">配布: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b7be0-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b7be0-110">変換する元の分布。</span><span class="sxs-lookup"><span data-stu-id="b7be0-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="b7be0-111">出力: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="b7be0-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="b7be0-112">によって指定された変換によってに関連する新しい分布 `distribution` `transform` 。</span><span class="sxs-lookup"><span data-stu-id="b7be0-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>