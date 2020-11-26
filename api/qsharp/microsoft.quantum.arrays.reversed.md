---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反転関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220435"
---
# <a name="reversed-function"></a>反転関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


入力配列と同じ要素が逆順に含まれる配列を作成します。

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>入力

### <a name="array--t"></a>配列: ' t []

逆の順序で要素をコピーする配列。



## <a name="output--t"></a>出力: ' t []

要素を格納している配列 `array[Length(array) - 1]` 。 `array[0]`.

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

配列要素の型。