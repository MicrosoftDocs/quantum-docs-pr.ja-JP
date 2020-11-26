---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211850"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="ed7b9-102">EstimateGradient 操作</span><span class="sxs-lookup"><span data-stu-id="ed7b9-102">EstimateGradient operation</span></span>

<span data-ttu-id="ed7b9-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ed7b9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ed7b9-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ed7b9-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="ed7b9-105">特定のモデルのシーケンシャル分類器のトレーニンググラデーションと、エンコードされた入力を推定します。</span><span class="sxs-lookup"><span data-stu-id="ed7b9-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="ed7b9-106">入力</span><span class="sxs-lookup"><span data-stu-id="ed7b9-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="ed7b9-107">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="ed7b9-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="ed7b9-108">グラデーションを推定するシーケンシャルモデル。</span><span class="sxs-lookup"><span data-stu-id="ed7b9-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="ed7b9-109">エンコード入力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="ed7b9-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="ed7b9-110">状態準備操作にエンコードされたシーケンシャル分類子への入力。</span><span class="sxs-lookup"><span data-stu-id="ed7b9-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="ed7b9-111">nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed7b9-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed7b9-112">グラデーションの推定に使用する測定値の数。</span><span class="sxs-lookup"><span data-stu-id="ed7b9-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="ed7b9-113">出力: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ed7b9-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ed7b9-114">指定された入力パラメーターとモデルパラメーターにおけるトレーニンググラデーションの見積もり。</span><span class="sxs-lookup"><span data-stu-id="ed7b9-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed7b9-115">解説</span><span class="sxs-lookup"><span data-stu-id="ed7b9-115">Remarks</span></span>

<span data-ttu-id="ed7b9-116">この操作では、Hadamard テストとパラメーターシフト手法を一緒に使用して、グラデーションを見積もります。</span><span class="sxs-lookup"><span data-stu-id="ed7b9-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>