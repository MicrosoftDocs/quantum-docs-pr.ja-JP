---
uid: Microsoft.Quantum.Arrays.Subarray
title: サブ配列関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845431"
---
# <a name="subarray-function"></a>サブ配列関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列と場所のリストを受け取り、指定した場所に一致する元の配列の要素から新しい配列を作成します。

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="indices--int"></a>インデックス: [Int](xref:microsoft.quantum.lang-ref.int)[]

サブ配列を定義するために使用される整数のリスト。


### <a name="array--t"></a>配列: ' t []

上の要素の配列 `'T` 。



## <a name="output--t"></a>出力: ' t []

`out`インデックスがサブ配列に対応する要素の配列 `out[idx] == array[indices[idx]]` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。

## <a name="remarks"></a>解説

関数は、ジェネリック型に対して定義されます。つまり、配列と、サブ配列を定義している `'T[]` 場所のリストがある場合は、そのように定義されます。 `Int[]`
サブ配列の構築は、参照を維持するのではなく、指定された配列の新しいディープコピーを生成することに基づいています。

`Length(indices) < Length(array)`の場合、この関数はのサブセットを返し `array` ます。 一方、に `indices` 繰り返し要素が含まれている場合は、の対応する要素も `array` 同様に繰り返されます。
`indices`との `array` 長さが同じである場合、この関数はの順列を提供 `array` します。