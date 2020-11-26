---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219857"
---
# <a name="zip-function"></a>Zip 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip は非推奨となりました。 代わりに、<xref:Microsoft.Quantum.Arrays.Zipped> を使用してください。

2つの配列を指定すると、は、各ペアに各元の配列の要素が含まれるように、ペアの新しい配列を返します。

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>入力

### <a name="left--t"></a>左: \ []

各組の最初の要素の値を格納している配列。


### <a name="right--u"></a>right: ' U []

各組の2番目の要素の値を格納している配列。



## <a name="output--tu"></a>出力: (' U '、' U) []

各のフォームのペアを格納 `(left[idx], right[idx])` している配列 `idx` 。 2つの配列が等しくない場合、出力は入力の短い方の長さになります。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

左の配列要素の型。
### <a name="u"></a>' U

正しい配列要素の型。

## <a name="see-also"></a>参照

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- [Microsoft.................](xref:Microsoft.Quantum.Arrays.Unzipped)