---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719203"
---
# <a name="foreach-operation"></a>ForEach 操作

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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