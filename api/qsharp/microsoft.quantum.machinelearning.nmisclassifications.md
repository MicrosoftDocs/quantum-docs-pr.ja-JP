---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: N誤分類関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853914"
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

## <a name="example"></a>例

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```