---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 関数の解凍
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845382"
---
# <a name="unzipped-function"></a>関数の解凍

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


2組の配列を指定すると、2つの配列の組を返します。各配列には、入力配列の組の要素が含まれます。

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>入力

### <a name="arr--tu"></a>arr: (' U '、' U) []

2つのタプルを含む配列



## <a name="output--tu"></a>出力: (' t [], ' U [])

2つの配列 (最初の1つは入力タプルの最初の要素、2つ目は入力タプルの2番目の要素を含んでいます)。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

各組の最初の要素の型
### <a name="u"></a>' U

各組の2番目の要素の型

## <a name="example"></a>例

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a>参照

- [Microsoft.Quantum.Arrays.Zip中](xref:Microsoft.Quantum.Arrays.Zipped)