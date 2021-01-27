---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Moスタンドテール関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845604"
---
# <a name="mostandtail-function"></a>Moスタンドテール関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


配列の最後の要素以外のすべてのタプルを返します。

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>入力

### <a name="array--a"></a>配列: ' A []

少なくとも1つの要素を含む配列。



## <a name="output--aa"></a>出力: (' A [], ' A)

配列の1つ以上の最後の要素のタプル。

## <a name="type-parameters"></a>型パラメーター

### <a name="a"></a>' A

配列要素の型。