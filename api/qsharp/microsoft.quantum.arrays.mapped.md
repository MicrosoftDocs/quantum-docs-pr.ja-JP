---
uid: Microsoft.Quantum.Arrays.Mapped
title: マップされた関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845685"
---
# <a name="mapped-function"></a>マップされた関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列と、配列の要素に対して定義されている関数を指定すると、関数の下にある元の配列のイメージで構成される新しい配列を返します。

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>入力

### <a name="mapper--t---u"></a>マッパー: > ' U

`'T` `'U` 要素をマップするために使用されるからへの関数。


### <a name="array--t"></a>配列: ' t []

上の要素の配列 `'T` 。



## <a name="output--u"></a>出力: ' U []

`'U[]`関数によってマップされる要素の配列 `mapper` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。
### <a name="u"></a>' U

関数の結果の型 `mapper` 。

## <a name="remarks"></a>解説

関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は、 `'T[]` `mapper: 'T -> 'U` 配列の要素をマップし、型の新しい配列を生成でき `'U[]` ます。