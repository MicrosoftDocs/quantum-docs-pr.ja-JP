---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709774"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="dd969-102">EstimateClassificationProbability 操作</span><span class="sxs-lookup"><span data-stu-id="dd969-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="dd969-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dd969-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dd969-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dd969-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dd969-105">サンプルとシーケンシャル分類子が指定されている場合、は、指定されたサンプルの分類子の出力を繰り返し測定することで、そのサンプルの分類確率を推定します。</span><span class="sxs-lookup"><span data-stu-id="dd969-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="dd969-106">入力</span><span class="sxs-lookup"><span data-stu-id="dd969-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="dd969-107">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dd969-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dd969-108">サンプルを状態準備操作にエンコードするときに許容される許容範囲。</span><span class="sxs-lookup"><span data-stu-id="dd969-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="dd969-109">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="dd969-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="dd969-110">指定されたサンプルの分類確率を見積もるために使用されるシーケンシャルモデル。</span><span class="sxs-lookup"><span data-stu-id="dd969-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="dd969-111">サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dd969-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dd969-112">分類するサンプルの特徴ベクター。</span><span class="sxs-lookup"><span data-stu-id="dd969-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="dd969-113">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dd969-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dd969-114">分類確率の推定に使用する測定値の数。</span><span class="sxs-lookup"><span data-stu-id="dd969-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="dd969-115">出力: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="dd969-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="dd969-116">指定されたサンプルの分類確率の推定値。</span><span class="sxs-lookup"><span data-stu-id="dd969-116">An estimate of the classification probability for the given sample.</span></span>