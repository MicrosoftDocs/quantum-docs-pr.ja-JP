---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions ユーザー定義型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722378"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="e4f29-102">TrainingOptions ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="e4f29-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="e4f29-103">名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="e4f29-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="e4f29-104">パック [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4f29-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4f29-105">トレーニングクォンタム分類子で使用されるオプションのコレクション。</span><span class="sxs-lookup"><span data-stu-id="e4f29-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="e4f29-106">名前付き項目</span><span class="sxs-lookup"><span data-stu-id="e4f29-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="e4f29-107">LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4f29-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e4f29-108">トレーニング手順でモデルパラメーターを更新するときに、グラデーションをスケールする学習速度。</span><span class="sxs-lookup"><span data-stu-id="e4f29-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="e4f29-109">Tolerance: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4f29-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e4f29-110">サンプルをクォンタム状態として準備するときに使用する近似の許容範囲。</span><span class="sxs-lookup"><span data-stu-id="e4f29-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="e4f29-111">MinibatchSize: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4f29-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4f29-112">各トレーニング minibatch で使用するサンプルの数。</span><span class="sxs-lookup"><span data-stu-id="e4f29-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="e4f29-113">NMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4f29-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4f29-114">分類の確率を推定するために、各分類の結果を測定する回数。</span><span class="sxs-lookup"><span data-stu-id="e4f29-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="e4f29-115">MaxEpochs: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4f29-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4f29-116">各モデルをトレーニングするエポックの最大数。</span><span class="sxs-lookup"><span data-stu-id="e4f29-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="e4f29-117">MaxStalls: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4f29-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4f29-118">失敗するまでにトレーニングエポックが停止できる最大回数 (約ゼログラデーション)。</span><span class="sxs-lookup"><span data-stu-id="e4f29-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="e4f29-119">StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e4f29-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e4f29-120">更新を再試行する前に、停止したモデルのスケールを変更する量。</span><span class="sxs-lookup"><span data-stu-id="e4f29-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="e4f29-121">ScoringPeriod: [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e4f29-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e4f29-122">スコアリングポイント間で実行されるグラデーションステップの数。</span><span class="sxs-lookup"><span data-stu-id="e4f29-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="e4f29-123">最適な精度を得るには、を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="e4f29-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="e4f29-124">VerboseMessage: [文字列](xref:microsoft.quantum.lang-ref.string) -> [単位](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e4f29-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="e4f29-125">詳細なフィードバックを提供するために使用できる関数。</span><span class="sxs-lookup"><span data-stu-id="e4f29-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="e4f29-126">解説</span><span class="sxs-lookup"><span data-stu-id="e4f29-126">Remarks</span></span>

<span data-ttu-id="e4f29-127">この UDT を直接作成することはできません。代わりに、を呼び出し、演算子を使用して @"microsoft.quantum.machinelearning.defaulttrainingoptions" `w/` 異なる既定値をオーバーライドすることによって指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4f29-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="e4f29-128">たとえば、10万の測定値と最大8個のトレーニングエポックを使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e4f29-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="e4f29-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4f29-129">References</span></span>

- [<span data-ttu-id="e4f29-130">arXiv: 1804.00633</span><span class="sxs-lookup"><span data-stu-id="e4f29-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)