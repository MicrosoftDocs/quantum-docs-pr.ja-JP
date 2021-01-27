---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848587"
---
# <a name="foreach-operation"></a>ForEach 操作

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列と、配列の要素に対して定義されている操作が指定された場合、は、操作の下にある元の配列のイメージで構成される新しい配列を返します。

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>入力

### <a name="action--t--u"></a>アクション: ' t => ' U 

`'T` `'U` 各要素に適用されるからへの操作。


### <a name="array--t"></a>配列: ' t []

上の要素の配列 `'T` 。



## <a name="output--u"></a>出力: ' U []

`'U[]`操作によってマップされる要素の配列 `action` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。
### <a name="u"></a>' U

操作の結果の種類 `action` 。

## <a name="remarks"></a>解説

この操作は、ジェネリック型に対して定義されます。つまり、配列と操作がある場合は、 `'T[]` `action : 'T -> 'U` 配列の要素をマップし、型の新しい配列を生成でき `'U[]` ます。