---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719054"
---
# <a name="mappedbyindex-function"></a>MappedByIndex 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列と、配列のインデックス付き要素に対して定義された関数を指定すると、関数の下にある元の配列のイメージで構成される新しい配列を返します。

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>入力

### <a name="mapper--intt---u"></a>マッパー: ([Int](xref:microsoft.quantum.lang-ref.int), t)-> ' U

`(Int, 'T)` `'U` 要素とそのインデックスをマップするために使用されるからへの関数。


### <a name="array--t"></a>配列: ' t []

上の要素の配列 `'T` 。



## <a name="output--u"></a>出力: ' U []

`'U[]`関数によってマップされる要素の配列 `mapper` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。
### <a name="u"></a>' U

関数の結果の型 `mapper` 。

## <a name="see-also"></a>参照

- [Microsoft. Quantum. マップ](xref:Microsoft.Quantum.Arrays.Mapped)