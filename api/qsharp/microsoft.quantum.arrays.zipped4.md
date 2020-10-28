---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 413b415288170b4a6bffbb773e3277cdb47bdbbe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718682"
---
# <a name="zipped4-function"></a>Zipped4 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


4つの配列がある場合、4組の新しい配列を返して、各4組に各元の配列の要素が格納されるようにします。

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>入力

### <a name="first--t1"></a>1: 1 []

各組の最初の要素の値を格納している配列。


### <a name="second--t2"></a>2番目: t 2 []

各組の2番目の要素の値を格納している配列。


### <a name="third--t3"></a>3番目: t 3 []

各組の3番目の要素の値を格納している配列。


### <a name="fourth--t4"></a>4番目: t 4 []

各組の4番目の要素の値を格納している配列。



## <a name="output--t1t2t3t4"></a>出力: (1、2、t 3、t 4) []

それぞれの形式の4組のを格納 `(first[idx], second[idx], third[idx], fourth[idx])` している配列 `idx` 。 4つの配列の長さが等しくない場合、出力は入力の短い方の長さになります。

## <a name="type-parameters"></a>型パラメーター

### <a name="t1"></a>1

最初の配列要素の型。
### <a name="t2"></a>T 2

2番目の配列要素の型。
### <a name="t3"></a>T 3

3番目の配列要素の型。
### <a name="t4"></a>T 4

4番目の配列要素の型。

## <a name="see-also"></a>参照

- [Microsoft.Quantum.Arrays.Zip中](xref:Microsoft.Quantum.Arrays.Zipped)
- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)