---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 列挙関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848123"
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

## <a name="example"></a>例

次の `for` ループは同等です。

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```