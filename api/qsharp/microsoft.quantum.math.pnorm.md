---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194731"
---
# <a name="pnorm-function"></a>PNorm 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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