---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 誤分類関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211680"
---
# <a name="misclassifications-function"></a>誤分類関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


一連の推定ラベルと一連の正しいラベルが指定されている場合、ラベルの各セットが異なる場所のインデックスを返します。

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>入力

### <a name="inferredlabels--int"></a>inferredLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]

特定のトレーニングまたは検証セットに対して推論されるラベル。


### <a name="actuallabels--int"></a>actualLabels: [Int](xref:microsoft.quantum.lang-ref.int)[]

指定されたトレーニングまたは検証セットの真のラベル。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

などのインデックスの配列 `idx` `inferredLabels[idx] != actualLabels[idx]` 。