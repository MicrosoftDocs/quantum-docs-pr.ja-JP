---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列挙関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221421"
---
# <a name="enumerated-function"></a>列挙関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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