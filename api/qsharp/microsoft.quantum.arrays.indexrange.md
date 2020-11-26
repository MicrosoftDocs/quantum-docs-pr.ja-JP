---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220945"
---
# <a name="indexrange-function"></a>IndexRange 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

Package: [Microsoft.](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core) ....... コア


配列を指定した場合は、その配列のインデックスに対する範囲を返します。 for ループでの使用に適しています。

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>入力

### <a name="array--telement"></a>配列: ' TElement []

インデックスの範囲を返す対象の配列。



## <a name="output--range"></a>出力: [範囲](xref:microsoft.quantum.lang-ref.range)

配列のすべてのインデックスの範囲。

## <a name="type-parameters"></a>型パラメーター

### <a name="telement"></a>' TElement '

配列の要素の型。