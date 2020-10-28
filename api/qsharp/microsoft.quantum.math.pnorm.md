---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722299"
---
# <a name="pnorm-function"></a>PNorm 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


`L(p)`のベクトルの基準を返し `Double` ます。

つまり、$ $x 型の $ が指定されている場合、 `Double[]` $-$p $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $ が返されます。

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>入力

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

指数は、$p $-基準で $ $p ます。


### <a name="array--double"></a>array: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)

$P $-標準 $ \| x \| _p $。