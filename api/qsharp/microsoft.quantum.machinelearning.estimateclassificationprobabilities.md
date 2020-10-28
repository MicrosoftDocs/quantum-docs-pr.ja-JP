---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709788"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="84a4b-102">EstimateClassificationProbabilities 操作</span><span class="sxs-lookup"><span data-stu-id="84a4b-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="84a4b-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="84a4b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="84a4b-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="84a4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="84a4b-105">一連のサンプルと連続した分類子を指定すると、は各サンプルの分類子の出力を繰り返し測定することで、これらのサンプルの分類確率を推定します。</span><span class="sxs-lookup"><span data-stu-id="84a4b-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="84a4b-106">入力</span><span class="sxs-lookup"><span data-stu-id="84a4b-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="84a4b-107">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="84a4b-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="84a4b-108">サンプルを状態準備操作にエンコードするときに許容される許容範囲。</span><span class="sxs-lookup"><span data-stu-id="84a4b-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="84a4b-109">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="84a4b-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="84a4b-110">指定されたサンプルの分類確率の推定に使用されるシーケンシャルモデル。</span><span class="sxs-lookup"><span data-stu-id="84a4b-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="84a4b-111">サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="84a4b-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="84a4b-112">分類する各サンプルの特徴ベクトルの配列。</span><span class="sxs-lookup"><span data-stu-id="84a4b-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="84a4b-113">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="84a4b-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="84a4b-114">分類確率の推定に使用する測定値の数。</span><span class="sxs-lookup"><span data-stu-id="84a4b-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="84a4b-115">出力: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="84a4b-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="84a4b-116">指定された各サンプルの分類確率の見積もりの配列。</span><span class="sxs-lookup"><span data-stu-id="84a4b-116">An array of estimates of the classification probability for each given sample.</span></span>