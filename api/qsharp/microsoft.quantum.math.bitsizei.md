---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7cfe03908a8a394fc8ceb1c9facbf02f3db2d48
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723195"
---
# <a name="bitsizei-function"></a>BitSizeI 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パック [](https://nuget.org/packages/)


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