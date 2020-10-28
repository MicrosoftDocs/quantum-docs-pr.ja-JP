---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719287"
---
# <a name="equala-function"></a>EqualA 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


同じ型の2つの配列と、配列の要素のペアに対して定義されている述語を指定すると、配列が等しいかどうかがチェックされます。

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>入力

### <a name="equal--tt---bool"></a>equal: (t, t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)

`('T, 'T)` `Bool` 配列の2つの要素が等しいかどうかを確認するために使用されるタプルから関数。


### <a name="array1--t"></a>配列 1: t []

比較する最初の配列。


### <a name="array2--t"></a>配列名: ' t []

比較する2番目の配列。



## <a name="output--bool"></a>出力: [Bool](xref:microsoft.quantum.lang-ref.bool)

`true`とが等しい場合にのみ、値を指定し `array1` `array2` ます。
つまり、両方の配列の長さが同じで、すべての要素がで定義されたとおりに等しい場合です `equal` 。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各配列の要素の型。

## <a name="remarks"></a>解説

この関数は、ジェネリック型に対して定義されています。つまり、2つの配列と関数がある場合、 `'T[]` `equal: ('T, 'T) -> Bool` この関数は、 `Bool` 配列が等しいかどうかを示す値を返します。
2つの配列が等しいと見なされるには、長さが同じで、配列内の同じ位置にある要素が等しい必要があります。