---
uid: Microsoft.Quantum.Arrays.Any
title: すべての関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846275"
---
# <a name="any-function"></a>すべての関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列と、配列の要素に対して定義された述語が指定されている場合、配列の少なくとも1つの要素が述語を満たすかどうかを確認します。

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>入力

### <a name="predicate--t---bool"></a>述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)

`'T` `Bool` 要素のチェックに使用されるからへの関数。


### <a name="array--t"></a>配列: ' t []

上の要素の配列 `'T` 。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`すべての要素に適用される述語の関数または関数の値。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。

## <a name="example"></a>例

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a>解説

関数は、ジェネリック型に対して定義されます。つまり、配列と関数がある場合は、一部の要素が満たされるかどうか `'T[]` `predicate: 'T -> Bool` `Bool` を示す値を生成でき `predicate` ます。