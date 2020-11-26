---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: N誤分類関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196312"
---
# <a name="nmisclassifications-function"></a>N誤分類関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パッケージ: [Microsoft. Quantum.](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


一連の推定ラベルと一連の正しいラベルが指定されると、によって、各ラベルのセットが異なるインデックスの数が返されます。

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>入力

### <a name="proposed--int"></a>提案済み: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>実際: [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

などのインデックスの数 `idx` `inferredLabels[idx] != actualLabels[idx]` 。