---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848408"
---
# <a name="inferredlabels-function"></a>InferredLabels 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


分類確率の配列とバイアスを指定すると、各確率から推論されたラベルが返されます。

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>入力

### <a name="bias--double"></a>バイアス: [Double](xref:microsoft.quantum.lang-ref.double)

2つのクラス間のバイアス (通常は分類器のトレーニングの結果)。


### <a name="probabilities--double"></a>確率: [Double](xref:microsoft.quantum.lang-ref.double)[]

一連のサンプルの分類確率の配列。通常は、分類の頻度を推定した結果として得られます。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

各分類確率から推論されるラベル。