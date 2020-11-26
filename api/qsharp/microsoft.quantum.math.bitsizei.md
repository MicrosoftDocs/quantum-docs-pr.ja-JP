---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195853"
---
# <a name="bitsizei-function"></a>BitSizeI 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


負でない整数の場合 `a` 、はを表すために必要なビット数を返し `a` ます。

つまり、$a < 2 ^ n $ である $n $ の最小値を返します。

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>入力

### <a name="a--int"></a>a: [Int](xref:microsoft.quantum.lang-ref.int)

ビットサイズを計算する整数。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

のビットサイズ `a` 。