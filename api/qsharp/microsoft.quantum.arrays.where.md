---
uid: Microsoft.Quantum.Arrays.Where
title: Where 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219925"
---
# <a name="where-function"></a>Where 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


述語と配列が指定されている場合、述語が true である配列のインデックスを返します。

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a>入力

### <a name="predicate--t---bool"></a>述語: > [Bool](xref:microsoft.quantum.lang-ref.bool)

`'T`要素をフィルター処理するために使用されるブール値からブール型への関数。


### <a name="array--t"></a>配列: ' t []

上の要素の配列 `'T` 。



## <a name="output--int"></a>出力: [Int](xref:microsoft.quantum.lang-ref.int)[]

が true であるインデックスの配列。 `predicate`

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

要素の型 `array` 。