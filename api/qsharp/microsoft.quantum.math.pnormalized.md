---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854850"
---
# <a name="pnormalized-function"></a>PNormalized 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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