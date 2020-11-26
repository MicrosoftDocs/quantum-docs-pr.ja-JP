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
# <a name="estimategradient-operation"></a>EstimateGradient 操作

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


特定のモデルのシーケンシャル分類器のトレーニンググラデーションと、エンコードされた入力を推定します。

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>入力

### <a name="model--sequentialmodel"></a>モデル: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

グラデーションを推定するシーケンシャルモデル。


### <a name="encodedinput--stategenerator"></a>エンコード入力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

状態準備操作にエンコードされたシーケンシャル分類子への入力。


### <a name="nmeasurements--int"></a>nMeasurements: [Int](xref:microsoft.quantum.lang-ref.int)

グラデーションの推定に使用する測定値の数。



## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)[]

指定された入力パラメーターとモデルパラメーターにおけるトレーニンググラデーションの見積もり。

## <a name="remarks"></a>解説

この操作では、Hadamard テストとパラメーターシフト手法を一緒に使用して、グラデーションを見積もります。