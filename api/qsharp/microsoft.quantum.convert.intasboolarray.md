---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833302"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


返された配列に対してリトルエンディアン表現を使用して、負でない整数のバイナリ表現を生成します。

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>入力

### <a name="number--int"></a>数値: [Int](xref:microsoft.quantum.lang-ref.int)

ブール値の配列に変換する負でない整数。


### <a name="bits--int"></a>ビット: [Int](xref:microsoft.quantum.lang-ref.int)

のバイナリ表現に含まれるビット数 `number` 。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

を表すブール値の配列 `number` 。

## <a name="remarks"></a>解説

入力は `bits` 0 ~ 63 の範囲で指定する必要があります。
入力は `number` 0 から $ 2 ^ {\texttt{bits}}-$1 の間でなければなりません。