---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: TrainSequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711305"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="ac5d0-102">TrainSequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="ac5d0-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="ac5d0-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ac5d0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ac5d0-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac5d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac5d0-105">シーケンシャル分類子の構造に基づいて、指定されたラベル付きトレーニングセットで分類器をトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="ac5d0-106">入力</span><span class="sxs-lookup"><span data-stu-id="ac5d0-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="ac5d0-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="ac5d0-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="ac5d0-108">トレーニング中に開始点として使用されるモデルの配列。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="ac5d0-109">サンプル: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="ac5d0-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="ac5d0-110">トレーニングを実行するために使用される、ラベル付けされたトレーニングデータのセット。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="ac5d0-111">オプション: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="ac5d0-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="ac5d0-112">トレーニング時に使用する構成詳細については、「」を参照してください @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" 。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="ac5d0-113">trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="ac5d0-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="ac5d0-114">トレーニング手順でトレーニングデータからサンプルを選択するときに使用するサンプリングスケジュール。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="ac5d0-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="ac5d0-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="ac5d0-116">最適な分類子スコアが生成された開始点を選択するときにトレーニングデータからサンプルを選択するときに使用するサンプリングスケジュール。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="ac5d0-117">出力: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span><span class="sxs-lookup"><span data-stu-id="ac5d0-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="ac5d0-118">指定された分類子のパラメーター化と、2つのクラス間のバイアス。これらは、指定された各開始点からの最適な結果に対応しています。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="ac5d0-119">最適な分類子モデルで観測されたミスの数。</span><span class="sxs-lookup"><span data-stu-id="ac5d0-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac5d0-120">参照</span><span class="sxs-lookup"><span data-stu-id="ac5d0-120">See Also</span></span>

- [<span data-ttu-id="ac5d0-121">Microsoft... TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="ac5d0-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="ac5d0-122">Microsoft... ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="ac5d0-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)