---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 332f9ea1753b539eba7b931d5b948b2a238d1abf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709872"
---
# <a name="nearlyequald-function"></a>NearlyEqualD 関数

名前空間: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

パック [](https://nuget.org/packages/)


2つの入力がほぼ等しい場合 (つまり、許容範囲が 1e-12 の範囲内) の場合にのみ true を返します。

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>入力

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

比較する最初の値。


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

比較する2番目の値。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true``a`がとほぼ等しい場合にのみ `b` 。

## <a name="remarks"></a>解説

同等のものを次に示します。

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```