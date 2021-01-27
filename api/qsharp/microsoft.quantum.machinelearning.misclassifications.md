---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: 誤分類関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853925"
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

## <a name="example"></a>例

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```