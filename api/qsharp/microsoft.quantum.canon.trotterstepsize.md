---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840068"
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