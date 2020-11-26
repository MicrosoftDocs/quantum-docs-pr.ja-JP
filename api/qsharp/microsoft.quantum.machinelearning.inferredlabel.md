---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211782"
---
# <a name="inferredlabel-function"></a>InferredLabel 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


分類の確率とバイアスが指定されている場合、はその確率から推論されたラベルを返します。

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>入力

### <a name="bias--double"></a>バイアス: [Double](xref:microsoft.quantum.lang-ref.double)

2つのクラス間のバイアス (通常は分類器のトレーニングの結果)。


### <a name="probability--double"></a>確率: [Double](xref:microsoft.quantum.lang-ref.double)

特定のサンプルの分類確率。通常は、その分類頻度を推定した結果になります。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

指定された分類確率から推論されるラベル。