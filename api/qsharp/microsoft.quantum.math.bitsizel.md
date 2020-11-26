---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 8b3d4cceb69619ed32977337fc0fe7401db38cbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211051"
---
# <a name="bitsizel-function"></a>BitSizeL 関数

名前空間: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


負でない整数の場合 `a` 、はを表すために必要なビット数を返し `a` ます。

つまり、$a < 2 ^ n $ である $n $ の最小値を返します。

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>入力

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

ビットサイズを計算する整数。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)

のビットサイズ `a` 。