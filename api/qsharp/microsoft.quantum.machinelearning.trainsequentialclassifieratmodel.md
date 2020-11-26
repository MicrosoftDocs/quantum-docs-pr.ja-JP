---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 02a300a2e1029d0e09aba19d090e15128fede717
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211467"
---
# <a name="trainsequentialclassifieratmodel-operation"></a><span data-ttu-id="2753f-102">TrainSequentialClassifierAtModel 操作</span><span class="sxs-lookup"><span data-stu-id="2753f-102">TrainSequentialClassifierAtModel operation</span></span>

<span data-ttu-id="2753f-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2753f-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2753f-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2753f-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2753f-105">シーケンシャルな分類子の構造に基づいて、特定のモデルから始まる特定のラベル付けされたトレーニングセットで分類器をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="2753f-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.</span></span>

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="2753f-106">入力</span><span class="sxs-lookup"><span data-stu-id="2753f-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="2753f-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="2753f-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="2753f-108">トレーニングの開始点として使用されるシーケンシャルモデル。</span><span class="sxs-lookup"><span data-stu-id="2753f-108">The sequential model to be used as a starting point for training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="2753f-109">サンプル: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="2753f-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="2753f-110">トレーニングを実行するために使用される、ラベル付けされたトレーニングデータのセット。</span><span class="sxs-lookup"><span data-stu-id="2753f-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="2753f-111">オプション: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="2753f-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="2753f-112">トレーニング時に使用する構成詳細については、「」を参照してください @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" 。</span><span class="sxs-lookup"><span data-stu-id="2753f-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="2753f-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="2753f-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="2753f-114">トレーニング手順でトレーニングデータからサンプルを選択するときに使用するサンプリングスケジュール。</span><span class="sxs-lookup"><span data-stu-id="2753f-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="2753f-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="2753f-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="2753f-116">最適な分類子スコアが生成された開始点を選択するときにトレーニングデータからサンプルを選択するときに使用するサンプリングスケジュール。</span><span class="sxs-lookup"><span data-stu-id="2753f-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="2753f-117">出力: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="2753f-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="2753f-118">指定された分類子のパラメーター化と、2つのクラス間のバイアス。これらは、指定された各開始点からの最適な結果に対応しています。</span><span class="sxs-lookup"><span data-stu-id="2753f-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="2753f-119">最適な分類子モデルで観測されたミスの数。</span><span class="sxs-lookup"><span data-stu-id="2753f-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="2753f-120">参照</span><span class="sxs-lookup"><span data-stu-id="2753f-120">See Also</span></span>

- [<span data-ttu-id="2753f-121">Microsoft... TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="2753f-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [<span data-ttu-id="2753f-122">Microsoft... ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="2753f-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)