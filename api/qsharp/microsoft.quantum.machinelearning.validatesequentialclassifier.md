---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: c100c5786b18996ce13067f1c4618cf0189578f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848979"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="78fe3-102">ValidateSequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="78fe3-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="78fe3-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="78fe3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="78fe3-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="78fe3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="78fe3-105">指定された一連のラベル付きサンプルに対して、特定のシーケンシャル分類子を検証します。</span><span class="sxs-lookup"><span data-stu-id="78fe3-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="78fe3-106">入力</span><span class="sxs-lookup"><span data-stu-id="78fe3-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="78fe3-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="78fe3-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="78fe3-108">検証するシーケンシャルモデル。</span><span class="sxs-lookup"><span data-stu-id="78fe3-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="78fe3-109">サンプル: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="78fe3-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="78fe3-110">指定されたモデルを検証するために使用するサンプル。</span><span class="sxs-lookup"><span data-stu-id="78fe3-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="78fe3-111">tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78fe3-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78fe3-112">各サンプルをシーケンシャル分類器への入力としてエンコードするときに使用する近似の許容範囲。</span><span class="sxs-lookup"><span data-stu-id="78fe3-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="78fe3-113">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="78fe3-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="78fe3-114">各サンプルの分類に使用する測定値の数。</span><span class="sxs-lookup"><span data-stu-id="78fe3-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="78fe3-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="78fe3-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="78fe3-116">検証セットからサンプルを描画するスケジュール。</span><span class="sxs-lookup"><span data-stu-id="78fe3-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="78fe3-117">出力: [Validationresults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="78fe3-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="78fe3-118">指定された検証の結果。</span><span class="sxs-lookup"><span data-stu-id="78fe3-118">The results of the given validation.</span></span>