---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713456"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パック [](https://nuget.org/packages/)


返された配列に対してリトルエンディアン表現を使用して、正の整数のバイナリ表現を生成します。

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a>入力

### <a name="number--int"></a>数値: [Int](xref:microsoft.quantum.lang-ref.int)

ブール値の配列に変換する正の整数。


### <a name="bits--int"></a>ビット: [Int](xref:microsoft.quantum.lang-ref.int)

のバイナリ表現に含まれるビット数 `number` 。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)[]

を表すブール値の配列 `number` 。

## <a name="remarks"></a>解説

入力は `bits` 0 ~ 63 の範囲で指定する必要があります。
入力は `number` 0 から $ 2 ^ {\texttt{bits}}-$1 の間でなければなりません。