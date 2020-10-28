---
uid: Microsoft.Quantum.Arithmetic.IdenticalPointPosFactFxP
title: IdenticalPointPosFactFxP 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IdenticalPointPosFactFxP
qsharp.summary: Assert that all fixed-point numbers in the provided array have identical point positions when counting from the least- significant bit. I.e., number of bits minus point position must be constant for all fixed-point numbers in the array.
ms.openlocfilehash: 0b285ce980ca1abbc3eb20838389a6f49835e742
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721118"
---
# <a name="identicalpointposfactfxp-function"></a>IdenticalPointPosFactFxP 関数

名前空間: [Microsoft. Quantum. 算術](xref:Microsoft.Quantum.Arithmetic)

パック [](https://nuget.org/packages/)


指定された配列内のすべての固定小数点数が、最下位ビットからカウントされるときに同一のポイント位置を持つことをアサートします。 つまり、ビット数からポイント位置を引いた値は、配列内のすべての固定小数点数に対して定数である必要があります。

```qsharp
function IdenticalPointPosFactFxP (fixedPoints : Microsoft.Quantum.Arithmetic.FixedPoint[]) : Unit
```


## <a name="input"></a>入力

### <a name="fixedpoints--fixedpoint"></a>fixedPoints: [Fixedpoints](xref:Microsoft.Quantum.Arithmetic.FixedPoint)[]

互換性をチェックするクォンタム固定小数点数の配列 (アサーションを使用)。



## <a name="output--unit"></a>出力: [単位](xref:microsoft.quantum.lang-ref.unit)

