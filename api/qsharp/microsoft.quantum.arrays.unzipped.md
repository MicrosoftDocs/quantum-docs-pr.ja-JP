---
uid: Microsoft.Quantum.Arrays.Unzipped
title: 関数の解凍
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219959"
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

## <a name="see-also"></a>参照

- [Microsoft.Quantum.Arrays.Zip中](xref:Microsoft.Quantum.Arrays.Zipped)