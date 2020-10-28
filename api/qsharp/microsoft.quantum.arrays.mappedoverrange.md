---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719042"
---
# <a name="mappedoverrange-function"></a>MappedOverRange 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


入力として整数を受け取る範囲と関数を指定した場合は、関数の下の範囲値のイメージで構成される新しい配列を返します。

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>入力

### <a name="mapper--int---t"></a>マッパー: [Int](xref:microsoft.quantum.lang-ref.int) -> t

`Int` `'T` 範囲値をマップするために使用されるからへの関数。


### <a name="range--range"></a>範囲: [範囲](xref:microsoft.quantum.lang-ref.range)

整数の範囲。



## <a name="output--t"></a>出力: ' t []

`'T[]`関数によってマップされる要素の配列 `mapper` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

関数の結果の型 `mapper` 。

## <a name="remarks"></a>解説

関数は、ジェネリック型に対して定義されます。つまり、関数がある場合は、 `mapper: Int -> 'T` 範囲の値をマップし、型の配列を生成でき `'T[]` ます。

## <a name="see-also"></a>参照

- [Microsoft. Quantum. マップ](xref:Microsoft.Quantum.Arrays.Mapped)