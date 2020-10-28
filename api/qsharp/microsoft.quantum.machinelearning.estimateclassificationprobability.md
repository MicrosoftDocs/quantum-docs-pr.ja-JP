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
# <a name="estimateclassificationprobability-operation"></a>EstimateClassificationProbability 操作

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


サンプルとシーケンシャル分類子が指定されている場合、は、指定されたサンプルの分類子の出力を繰り返し測定することで、そのサンプルの分類確率を推定します。

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a>入力

### <a name="tolerance--double"></a>tolerance: [Double](xref:microsoft.quantum.lang-ref.double)

サンプルを状態準備操作にエンコードするときに許容される許容範囲。


### <a name="model--sequentialmodel"></a>モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

指定されたサンプルの分類確率を見積もるために使用されるシーケンシャルモデル。


### <a name="sample--double"></a>サンプル: [Double](xref:microsoft.quantum.lang-ref.double)[]

分類するサンプルの特徴ベクター。


### <a name="nmeasurements--int"></a>nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

分類確率の推定に使用する測定値の数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

指定されたサンプルの分類確率の推定値。