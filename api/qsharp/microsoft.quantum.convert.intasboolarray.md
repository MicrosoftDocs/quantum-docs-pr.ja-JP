---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224345"
---
# <a name="intasboolarray-function"></a>IntAsBoolArray 関数

名前空間: [Microsoft. Quantum. 変換](xref:Microsoft.Quantum.Convert)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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