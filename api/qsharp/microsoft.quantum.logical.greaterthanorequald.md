---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0c9fa353b549d3c137beac3bcc3cfb0e742f6d07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197808"
---
# <a name="greaterthanorequald-function"></a>GreaterThanOrEqualD 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


数値がもう1つの数値以上の場合にのみ true を返します。

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>入力

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

比較する最初の値。


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がより大きいか、またはと等しい場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```