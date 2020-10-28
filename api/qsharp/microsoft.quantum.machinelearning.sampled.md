---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: サンプリングされた関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 9f9f91bc50861c5b31a76e28050189d13efda71e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722425"
---
# <a name="sampled-function"></a><span data-ttu-id="e02c0-102">サンプリングされた関数</span><span class="sxs-lookup"><span data-stu-id="e02c0-102">Sampled function</span></span>

<span data-ttu-id="e02c0-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e02c0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e02c0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e02c0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e02c0-105">指定されたスケジュールを使用して、指定された配列をサンプリングします。</span><span class="sxs-lookup"><span data-stu-id="e02c0-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e02c0-106">入力</span><span class="sxs-lookup"><span data-stu-id="e02c0-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="e02c0-107">スケジュール: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="e02c0-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="e02c0-108">サンプリング値で使用するスケジュール。</span><span class="sxs-lookup"><span data-stu-id="e02c0-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="e02c0-109">値: ' t []</span><span class="sxs-lookup"><span data-stu-id="e02c0-109">values : 'T[]</span></span>

<span data-ttu-id="e02c0-110">サンプリングする値の配列。</span><span class="sxs-lookup"><span data-stu-id="e02c0-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="e02c0-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="e02c0-111">Output : 'T[]</span></span>

<span data-ttu-id="e02c0-112">指定されたスケジュールに従った値からの要素の配列。</span><span class="sxs-lookup"><span data-stu-id="e02c0-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e02c0-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="e02c0-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e02c0-114">&</span><span class="sxs-lookup"><span data-stu-id="e02c0-114">'T</span></span>

