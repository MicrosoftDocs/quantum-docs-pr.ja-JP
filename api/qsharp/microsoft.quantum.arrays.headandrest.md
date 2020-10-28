---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: ヘッド Andrest 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719179"
---
# <a name="headandrest-function"></a>ヘッド Andrest 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列の最初の要素と残りのすべての要素の組を返します。

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>入力

### <a name="array--a"></a>配列: ' A []

少なくとも1つの要素を含む配列。



## <a name="output--aa"></a>出力: (' A, ' A [])

配列の最初の要素と残りのすべての要素のタプル。

## <a name="type-parameters"></a>型パラメーター

### <a name="a"></a>' A

配列要素の型。