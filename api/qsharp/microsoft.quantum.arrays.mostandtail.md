---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: Moスタンドテール関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718994"
---
# <a name="mostandtail-function"></a>Moスタンドテール関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


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