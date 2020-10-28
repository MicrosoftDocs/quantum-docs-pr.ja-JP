---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列挙関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719306"
---
# <a name="enumerated-function"></a>列挙関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列が指定された場合、は、元の配列の要素と各要素のインデックスを含む新しい配列を返します。

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>入力

### <a name="array--telement"></a>配列: ' TElement []

要素が列挙される配列。



## <a name="output--inttelement"></a>出力: ([Int](xref:microsoft.quantum.lang-ref.int), ' telement) []

元の配列の要素とそのインデックスを含む新しい配列。

## <a name="type-parameters"></a>型パラメーター

### <a name="telement"></a>' TElement '

配列の要素の型。