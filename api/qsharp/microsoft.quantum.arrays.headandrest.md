---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: ヘッド Andrest 関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848558"
---
# <a name="headandrest-function"></a>ヘッド Andrest 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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