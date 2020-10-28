---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722285"
---
# <a name="pnormalized-function"></a>PNormalized 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


標準でのベクトルを正規化 `Double` `L(p)` します。

つまり、$ $x 型の配列を指定すると、 `Double[]` すべての要素が $p $-基準 $ x _p $ で除算された配列が返され \| \| ます。

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>入力

### <a name="p--double"></a>p: [Double](xref:microsoft.quantum.lang-ref.double)

指数は、$p $-基準で $ $p ます。


### <a name="array--double"></a>array: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>出力: [Double](xref:microsoft.quantum.lang-ref.double)[]

配列は、$-$p $ x _p $ で $x $ 正規化されて \| \| います。

## <a name="see-also"></a>参照

- [Microsoft. Quantum.](xref:Microsoft.Quantum.Math.PNorm)