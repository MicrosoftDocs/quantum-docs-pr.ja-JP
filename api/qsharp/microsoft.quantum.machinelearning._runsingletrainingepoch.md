---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 71780645a025972f11f32f8ba8fd94d098604f9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196754"
---
# <a name="_runsingletrainingepoch-operation"></a>_RunSingleTrainingEpoch 操作

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


データサンプルのサブセットに対して、順次分類器トレーニングの1つのエポックを実行します。

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>入力

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples: ([Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)、[stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>スケジュール: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore: [Int](xref:microsoft.quantum.lang-ref.int)

スコアリングポイント間で実行されるグラデーションステップの数。
最適な精度を得るには、を1に設定します。


### <a name="options--trainingoptions"></a>オプション: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

トレーニングで使用するオプション。


### <a name="model--sequentialmodel"></a>モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

トレーニングされるシーケンシャルモデル。


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses: [Int](xref:microsoft.quantum.lang-ref.int)

以前のエポックで観察された誤分類の最大数。



## <a name="output--intsequentialmodel"></a>出力: ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

- このエポックに対して観測された誤分類の最小数。
- 新しい最適なシーケンシャルモデルが見つかりました。