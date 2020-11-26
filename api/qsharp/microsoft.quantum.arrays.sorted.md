---
uid: Microsoft.Quantum.Arrays.Sorted
title: Sorted 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: bd8b869e03c7f4687c456a944e07a811ae0d2ce2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220231"
---
# <a name="sorted-function"></a>Sorted 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列が指定された場合、は、指定された比較関数によって並べ替えられた配列の要素を返します。

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="comparison--tt---bool"></a>比較: (' t, ' t)-> [Bool](xref:microsoft.quantum.lang-ref.bool)

`a` `b` がの場合に、以下の2つの要素を比較する関数 `comparison(a, b)` `true` 。


### <a name="array--t"></a>配列: ' t []

並べ替える配列。



## <a name="output--t"></a>出力: ' t []



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `array` 。

## <a name="remarks"></a>解説

関数は `comparison` 推移的であると見なされ、 `comparison(a, b)` との場合はと `comparison(b, c)` 見なされ `comparison(a, c)` ます。 このプロパティがを保持していない場合、この関数の出力は正しくない可能性があります。

これは関数であるため、2つの要素が等しいと見なされた場合、つまり `comparison` `comparison(a, b)` とが `comparison(b, a)` 両方とも等しい場合でも、結果は完全に解釈され `true` ます。
特に、この関数によって実行される並べ替えは安定していることが保証されているので、2つの要素 `a` とが `b` 内で同じ順序で発生し、かつがの下に等しいと見なされると `array` `comparison` 、 `a` は出力の前にも表示され `b` ます。

次に例を示します。

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```