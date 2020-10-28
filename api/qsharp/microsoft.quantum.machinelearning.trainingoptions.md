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
# <a name="trainingoptions-user-defined-type"></a>TrainingOptions ユーザー定義型

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


トレーニングクォンタム分類子で使用されるオプションのコレクション。

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>名前付き項目

### <a name="learningrate--double"></a>LearningRate: [Double](xref:microsoft.quantum.lang-ref.double)

トレーニング手順でモデルパラメーターを更新するときに、グラデーションをスケールする学習速度。
### <a name="tolerance--double"></a>Tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

サンプルをクォンタム状態として準備するときに使用する近似の許容範囲。
### <a name="minibatchsize--int"></a>MinibatchSize: [Int](xref:microsoft.quantum.lang-ref.int)

各トレーニング minibatch で使用するサンプルの数。
### <a name="nmeasurements--int"></a>NMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

分類の確率を推定するために、各分類の結果を測定する回数。
### <a name="maxepochs--int"></a>MaxEpochs: [Int](xref:microsoft.quantum.lang-ref.int)

各モデルをトレーニングするエポックの最大数。
### <a name="maxstalls--int"></a>MaxStalls: [Int](xref:microsoft.quantum.lang-ref.int)

失敗するまでにトレーニングエポックが停止できる最大回数 (約ゼログラデーション)。
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor: [Double](xref:microsoft.quantum.lang-ref.double)

更新を再試行する前に、停止したモデルのスケールを変更する量。
### <a name="scoringperiod--int"></a>ScoringPeriod: [Int](xref:microsoft.quantum.lang-ref.int)

スコアリングポイント間で実行されるグラデーションステップの数。
最適な精度を得るには、を1に設定します。
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [文字列](xref:microsoft.quantum.lang-ref.string) -> [単位](xref:microsoft.quantum.lang-ref.unit)

詳細なフィードバックを提供するために使用できる関数。

## <a name="remarks"></a>解説

この UDT を直接作成することはできません。代わりに、を呼び出し、演算子を使用して @"microsoft.quantum.machinelearning.defaulttrainingoptions" `w/` 異なる既定値をオーバーライドすることによって指定する必要があります。

たとえば、10万の測定値と最大8個のトレーニングエポックを使用するには、次のようにします。

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>関連項目

- [arXiv: 1804.00633](https://arxiv.org/abs/1804.00633)