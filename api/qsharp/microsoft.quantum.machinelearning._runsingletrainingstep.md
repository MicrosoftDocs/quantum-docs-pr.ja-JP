---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingStep
title: _RunSingleTrainingStep 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingStep
qsharp.summary: attempts a single parameter update in the direction of mini batch gradient
ms.openlocfilehash: 2ee6dbbf26e8514ad59d156da12e0bcaca4ad7ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96212105"
---
# <a name="_runsingletrainingstep-operation"></a><span data-ttu-id="93980-102">_RunSingleTrainingStep 操作</span><span class="sxs-lookup"><span data-stu-id="93980-102">_RunSingleTrainingStep operation</span></span>

<span data-ttu-id="93980-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="93980-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="93980-104">パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="93980-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="93980-105">ミニバッチグラデーションの方向に1つのパラメーターの更新を試行します</span><span class="sxs-lookup"><span data-stu-id="93980-105">attempts a single parameter update in the direction of mini batch gradient</span></span>

```qsharp
operation _RunSingleTrainingStep (miniBatch : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel) : (Double, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="93980-106">入力</span><span class="sxs-lookup"><span data-stu-id="93980-106">Input</span></span>

### <a name="minibatch--labeledsamplestategenerator"></a><span data-ttu-id="93980-107">miniBatch: ([Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)、[stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="93980-107">miniBatch : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>

<span data-ttu-id="93980-108">ミニバッチ内のラベル付けされたサンプルのコンテナー</span><span class="sxs-lookup"><span data-stu-id="93980-108">container of labeled samples in the mini batch</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="93980-109">オプション: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="93980-109">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>




### <a name="model--sequentialmodel"></a><span data-ttu-id="93980-110">モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="93980-110">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--doublesequentialmodel"></a><span data-ttu-id="93980-111">出力: ([Double](xref:microsoft.quantum.lang-ref.double),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="93980-111">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

<span data-ttu-id="93980-112">(ユーティリティ、(新しい) パラメーター) ペア</span><span class="sxs-lookup"><span data-stu-id="93980-112">(utility, (new)parameters) pair</span></span>