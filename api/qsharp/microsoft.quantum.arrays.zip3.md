---
uid: Microsoft.Quantum.Arrays.Zip3
title: Array.zip3 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718723"
---
# <a name="zip3-function"></a>Array.zip3 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


> [!WARNING]
> Array.zip3 は非推奨となりました。 代わりに、<xref:Microsoft.Quantum.Arrays.Zipped3> を使用してください。

3つの配列を指定すると、3組の新しい配列が返されます。これにより、各3組には各元の配列の要素が含まれます。

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>入力

### <a name="first--t1"></a>1: 1 []

各組の最初の要素の値を格納している配列。


### <a name="second--t2"></a>2番目: t 2 []

各組の2番目の要素の値を格納している配列。


### <a name="third--t3"></a>3番目: t 3 []

各組の3番目の要素の値を格納している配列。



## <a name="output--t1t2t3"></a>出力: (1、2、t 3) []

各のフォームの3組のタプルを格納 `(first[idx], second[idx], third[idx])` している配列 `idx` 。 3つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。

## <a name="type-parameters"></a>型パラメーター

### <a name="t1"></a>1

最初の配列要素の型。
### <a name="t2"></a>T 2

2番目の配列要素の型。
### <a name="t3"></a>T 3

3番目の配列要素の型。

## <a name="see-also"></a>参照

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)