---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: N誤分類関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709737"
---
# <a name="nmisclassifications-function"></a>N誤分類関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


一連の推定ラベルと一連の正しいラベルが指定されると、によって、各ラベルのセットが異なるインデックスの数が返されます。

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>入力

### <a name="proposed--int"></a>提案済み: [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>実際: [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

などのインデックスの数 `idx` `inferredLabels[idx] != actualLabels[idx]` 。