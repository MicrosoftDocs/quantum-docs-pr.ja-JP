---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 4164c190cb19b6d3ea74d9803a77d2b19607279b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857153"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel 操作

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


シーケンシャルな分類子の構造に基づいて、特定のモデルから始まる特定のラベル付けされたトレーニングセットで分類器をトレーニングします。

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>入力

### <a name="model--sequentialmodel"></a>モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

トレーニングの開始点として使用されるシーケンシャルモデル。


### <a name="samples--labeledsample"></a>サンプル: [Labeledsample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

トレーニングを実行するために使用される、ラベル付けされたトレーニングデータのセット。


### <a name="options--trainingoptions"></a>オプション: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

トレーニング時に使用する構成詳細については、「」を参照してください @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" 。


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

トレーニング手順でトレーニングデータからサンプルを選択するときに使用するサンプリングスケジュール。


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

最適な分類子スコアが生成された開始点を選択するときにトレーニングデータからサンプルを選択するときに使用するサンプリングスケジュール。



## <a name="output--sequentialmodelint"></a>出力: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))

- 指定された分類子のパラメーター化と、2つのクラス間のバイアス。これらは、指定された各開始点からの最適な結果に対応しています。
- 最適な分類子モデルで観測されたミスの数。

## <a name="see-also"></a>参照

- [Microsoft... TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft... ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)