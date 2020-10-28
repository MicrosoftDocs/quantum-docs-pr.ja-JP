---
uid: Microsoft.Quantum.Arrays.All
title: All 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719479"
---
# <a name="all-function"></a>All 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列と、配列の要素に対して定義されている述語が指定されている場合、配列のすべての要素が述語を満たすかどうかを確認します。

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>入力

### <a name="predicate--t---bool"></a>述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)

`'T` `Bool` 要素のチェックに使用されるからへの関数。


### <a name="array--t"></a>配列: ' t []

上の要素の配列 `'T` 。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`すべての要素に適用される述語の関数と関数の値。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。

## <a name="remarks"></a>解説

関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は常に、 `'T[]` `predicate: 'T -> Bool` すべての要素が `Bool` 満たされるかどうかを示す値を生成でき `predicate` ます。