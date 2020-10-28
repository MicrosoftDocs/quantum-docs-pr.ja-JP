---
uid: Microsoft.Quantum.Arrays.Reversed
title: 反転関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718910"
---
# <a name="reversed-function"></a>反転関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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