---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845776"
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

## <a name="example"></a>例

次の `for` ループは同等です。

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```