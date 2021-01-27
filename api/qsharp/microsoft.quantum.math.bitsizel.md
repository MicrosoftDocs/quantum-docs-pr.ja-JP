---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: c94d873d7117fd2ee66226fab6d4bfc5b33bc46d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848910"
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