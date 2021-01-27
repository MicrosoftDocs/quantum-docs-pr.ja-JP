---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848416"
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