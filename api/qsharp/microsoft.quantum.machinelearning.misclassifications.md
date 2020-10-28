---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 誤分類関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723582"
---
# <a name="misclassifications-function"></a>誤分類関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


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