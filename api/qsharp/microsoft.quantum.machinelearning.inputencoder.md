---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709751"
---
# <a name="inputencoder-function"></a>InputEncoder 関数

名前空間: [Microsoft. Quantum の e ラーニング](xref:Microsoft.Quantum.MachineLearning)

パック [](https://nuget.org/packages/)


係数と許容範囲を指定すると、は、各係数を計算ベース状態の対応する振幅として準備する状態準備操作を返します。

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>入力

### <a name="coefficients--double"></a>係数: [Double](xref:microsoft.quantum.lang-ref.double)[]

入力状態にエンコードされる係数。



## <a name="output--stategenerator"></a>出力: [Stategenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

指定された係数を特定のレジスタの入力状態として準備する状態準備操作。