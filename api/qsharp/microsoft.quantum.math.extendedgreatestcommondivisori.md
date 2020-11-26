---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: Extendedグリーン Atestcommon区分 Sori 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 365e91e84add0d57d5a3cf203bbf23d96979b251
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195529"
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

## <a name="references"></a>リファレンス

- この実装は次のものに従っています。 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm