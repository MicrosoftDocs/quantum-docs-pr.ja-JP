---
uid: Microsoft.Quantum.Arrays.Head
title: Head 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Head
qsharp.summary: Returns the first element of the array.
ms.openlocfilehash: 7b26a9c414ab2caad70f96f3c26c2d1cf0b03e95
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719186"
---
# <a name="head-function"></a>Head 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列の最初の要素を返します。

```qsharp
function Head<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>入力

### <a name="array--a"></a>配列: ' A []

最初の要素を取得する対象の配列。 配列の長さは少なくとも1である必要があります。



## <a name="output--a"></a>出力: ' A

配列の最初の要素。

## <a name="type-parameters"></a>型パラメーター

### <a name="a"></a>' A

配列要素の型。