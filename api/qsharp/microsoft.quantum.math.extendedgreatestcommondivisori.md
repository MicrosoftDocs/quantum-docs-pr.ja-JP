---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: Extendedグリーン Atestcommon区分 Sori 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e86237f39e696485a3496f1c6dd571cd516214ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857552"
---
# <a name="extendedgreatestcommondivisori-function"></a>Extendedグリーン Atestcommon区分 Sori 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


$U \ cdot a + v/cdot b = \ 演算子 name{gcd} (a, b) $ のようなタプル $ (u, v) $ を計算します。 $-演算子名 {gcd} $ は、$a $ および $b $ の最も一般的な除数 $a です。 GCD は常に正の数値です。

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)

拡張された最も一般的な除数の計算対象となる最初の数値


### <a name="b--int"></a>b: [Int](xref:microsoft.quantum.lang-ref.int)

拡張された最も一般的な除数が計算されている2番目の数値



## <a name="output--intint"></a>出力: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

タプル $ (u, v) $ とプロパティ $u \ cdot a + v \ cdot b = \ 演算子 name{gcd} (a, b) $。

## <a name="references"></a>References

- この実装は次のものに従っています。 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm