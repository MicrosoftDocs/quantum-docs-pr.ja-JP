---
uid: Microsoft.Quantum.MachineLearning.Sampled
title: サンプリングされた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Sampled
qsharp.summary: Samples a given array, using the given schedule.
ms.openlocfilehash: 5dd599246847718f4f0411715585cb416595db9d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854941"
---
# <a name="sampled-function"></a><span data-ttu-id="728c2-102">サンプリングされた関数</span><span class="sxs-lookup"><span data-stu-id="728c2-102">Sampled function</span></span>

<span data-ttu-id="728c2-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="728c2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="728c2-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="728c2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="728c2-105">指定されたスケジュールを使用して、指定された配列をサンプリングします。</span><span class="sxs-lookup"><span data-stu-id="728c2-105">Samples a given array, using the given schedule.</span></span>

```qsharp
function Sampled<'T> (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, values : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="728c2-106">入力</span><span class="sxs-lookup"><span data-stu-id="728c2-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="728c2-107">スケジュール: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="728c2-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="728c2-108">サンプリング値で使用するスケジュール。</span><span class="sxs-lookup"><span data-stu-id="728c2-108">A schedule to use in sampling values.</span></span>


### <a name="values--t"></a><span data-ttu-id="728c2-109">値: ' t []</span><span class="sxs-lookup"><span data-stu-id="728c2-109">values : 'T[]</span></span>

<span data-ttu-id="728c2-110">サンプリングする値の配列。</span><span class="sxs-lookup"><span data-stu-id="728c2-110">An array of values to be sampled.</span></span>



## <a name="output--t"></a><span data-ttu-id="728c2-111">出力: ' t []</span><span class="sxs-lookup"><span data-stu-id="728c2-111">Output : 'T[]</span></span>

<span data-ttu-id="728c2-112">指定されたスケジュールに従った値からの要素の配列。</span><span class="sxs-lookup"><span data-stu-id="728c2-112">An array of elements from values, following the given schedule.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="728c2-113">型パラメーター</span><span class="sxs-lookup"><span data-stu-id="728c2-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="728c2-114">&</span><span class="sxs-lookup"><span data-stu-id="728c2-114">'T</span></span>

