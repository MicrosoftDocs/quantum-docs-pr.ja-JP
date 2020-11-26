---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: aa5b63e058e1ea726b0d4c6eca73078831daaf3b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204693"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize 関数

名前空間: [Microsoft. Quantum. キャノン](xref:Microsoft.Quantum.Canon)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Trotter シミュレーションアルゴリズムの再帰実装で Trotter ステップサイズを計算します。

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>入力

### <a name="order--int"></a>順序: [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>解説

この操作では、 [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139)とは異なるインデックス作成規則が使用されます。 特に、 `DecomposedIntoTimeStepsCA(_, 4)` _2 (0508139) のスカラー $p (-ラムダ) $ に対応します。