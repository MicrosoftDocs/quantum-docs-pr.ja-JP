---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719150"
---
# <a name="indexrange-function"></a>IndexRange 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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