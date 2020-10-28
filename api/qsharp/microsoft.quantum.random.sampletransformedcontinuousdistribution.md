---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723974"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="a9a01-102">SampleTransformedContinuousDistribution 操作</span><span class="sxs-lookup"><span data-stu-id="a9a01-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="a9a01-103">名前空間: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a9a01-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a9a01-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a9a01-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a9a01-105">変換された分布からサンプリングする内部専用操作。</span><span class="sxs-lookup"><span data-stu-id="a9a01-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="a9a01-106">部分的なアプリケーションでのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="a9a01-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="a9a01-107">入力</span><span class="sxs-lookup"><span data-stu-id="a9a01-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="a9a01-108">変換: [double](xref:microsoft.quantum.lang-ref.double) -> [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9a01-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="a9a01-109">配布: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="a9a01-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="a9a01-110">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a9a01-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

