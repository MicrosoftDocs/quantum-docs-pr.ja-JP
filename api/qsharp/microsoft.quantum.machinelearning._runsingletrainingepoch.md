---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720631"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="964db-102">_RunSingleTrainingEpoch 操作</span><span class="sxs-lookup"><span data-stu-id="964db-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="964db-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="964db-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="964db-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="964db-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="964db-105">データサンプルのサブセットに対して、順次分類器トレーニングの1つのエポックを実行します。</span><span class="sxs-lookup"><span data-stu-id="964db-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="964db-106">入力</span><span class="sxs-lookup"><span data-stu-id="964db-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="964db-107">encodedSamples: ([Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)、[stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="964db-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="964db-108">スケジュール: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="964db-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="964db-109">periodScore: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="964db-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="964db-110">スコアリングポイント間で実行されるグラデーションステップの数。</span><span class="sxs-lookup"><span data-stu-id="964db-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="964db-111">最適な精度を得るには、を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="964db-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="964db-112">オプション: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="964db-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="964db-113">トレーニングで使用するオプション。</span><span class="sxs-lookup"><span data-stu-id="964db-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="964db-114">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="964db-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="964db-115">トレーニングされるシーケンシャルモデル。</span><span class="sxs-lookup"><span data-stu-id="964db-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="964db-116">nPreviousBestMisses: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="964db-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="964db-117">以前のエポックで観察された誤分類の最大数。</span><span class="sxs-lookup"><span data-stu-id="964db-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="964db-118">出力: ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="964db-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="964db-119">このエポックに対して観測された誤分類の最小数。</span><span class="sxs-lookup"><span data-stu-id="964db-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="964db-120">新しい最適なシーケンシャルモデルが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="964db-120">The new best sequential model found.</span></span>