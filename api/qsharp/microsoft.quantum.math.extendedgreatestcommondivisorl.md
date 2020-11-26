---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: Extendedグリーン Atestcommon区分 Sorl 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: abbbd367859952180f181a245ca0754646529b18
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210711"
---
# <a name="extendedgreatestcommondivisorl-function"></a>Extendedグリーン Atestcommon区分 Sorl 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


$U \ cdot a + v/cdot b = \ 演算子 name{gcd} (a, b) $ のようなタプル $ (u, v) $ を計算します。 $-演算子名 {gcd} $ は、$a $ および $b $ の最も一般的な除数 $a です。 GCD は常に正の数値です。

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>入力

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

拡張された最も一般的な除数の計算対象となる最初の数値


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

拡張された最も一般的な除数が計算されている2番目の数値



## <a name="output--bigintbigint"></a>出力: ([bigint](xref:microsoft.quantum.lang-ref.bigint),[bigint](xref:microsoft.quantum.lang-ref.bigint))

タプル $ (u, v) $ とプロパティ $u \ cdot a + v \ cdot b = \ 演算子 name{gcd} (a, b) $。

## <a name="references"></a>リファレンス

- この実装は次のものに従っています。 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm