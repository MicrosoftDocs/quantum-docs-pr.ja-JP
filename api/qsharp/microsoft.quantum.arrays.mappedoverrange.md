---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845647"
---
# <a name="mappedoverrange-function"></a>MappedOverRange 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>例

次の例では、偶数の範囲に1を加算します。

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a>解説

関数は、ジェネリック型に対して定義されます。つまり、関数がある場合は、 `mapper: Int -> 'T` 範囲の値をマップし、型の配列を生成でき `'T[]` ます。

## <a name="see-also"></a>参照

- [Microsoft. Quantum. マップ](xref:Microsoft.Quantum.Arrays.Mapped)