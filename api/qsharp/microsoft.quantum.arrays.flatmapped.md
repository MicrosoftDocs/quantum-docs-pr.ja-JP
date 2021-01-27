---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848639"
---
# <a name="flatmapped-function"></a>FlatMapped 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列と、配列要素をいくつかの出力配列にマップする関数を指定すると、配列要素ごとに連結された出力配列が返されます。

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>入力

### <a name="mapper--tinput---toutput"></a>マッパー: ' > TInput ' TOutput []

`'TInput` `'TOutput[]` 配列要素をマップするために使用されるからへの関数。


### <a name="array--tinput"></a>配列: ' TInput []

要素の配列。



## <a name="output--toutput"></a>出力: ' TOutput []

の配列 `'TOutput[]` 。これは、マッピング関数によって生成されるすべての配列を連結したものです。

## <a name="type-parameters"></a>型パラメーター

### <a name="tinput"></a>'TInput

要素の型 `array` 。
### <a name="toutput"></a>'TOutput

関数は、 `mapper` この型の配列を返します。

## <a name="example"></a>例

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```