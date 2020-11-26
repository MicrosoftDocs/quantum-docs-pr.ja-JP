---
uid: Microsoft.Quantum.MachineLearning.ScheduleLength
title: ScheduleLength 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ScheduleLength
qsharp.summary: Returns the number of elements in a given sampling schedule.
ms.openlocfilehash: 008bdcdc0a7c0ad2775dea65ebba46556092beed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211595"
---
# <a name="schedulelength-function"></a><span data-ttu-id="61cbb-102">ScheduleLength 関数</span><span class="sxs-lookup"><span data-stu-id="61cbb-102">ScheduleLength function</span></span>

<span data-ttu-id="61cbb-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="61cbb-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="61cbb-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="61cbb-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="61cbb-105">指定されたサンプリングスケジュール内の要素の数を返します。</span><span class="sxs-lookup"><span data-stu-id="61cbb-105">Returns the number of elements in a given sampling schedule.</span></span>

```qsharp
function ScheduleLength (schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Int
```


## <a name="input"></a><span data-ttu-id="61cbb-106">入力</span><span class="sxs-lookup"><span data-stu-id="61cbb-106">Input</span></span>

### <a name="schedule--samplingschedule"></a><span data-ttu-id="61cbb-107">スケジュール: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="61cbb-107">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="61cbb-108">長さが返されるサンプリングスケジュール。</span><span class="sxs-lookup"><span data-stu-id="61cbb-108">A sampling schedule whose length is to be returned.</span></span>



## <a name="output--int"></a><span data-ttu-id="61cbb-109">出力: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61cbb-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61cbb-110">指定されたサンプリングスケジュール内の要素の数。</span><span class="sxs-lookup"><span data-stu-id="61cbb-110">The number of elements in the given sampling schedule.</span></span>