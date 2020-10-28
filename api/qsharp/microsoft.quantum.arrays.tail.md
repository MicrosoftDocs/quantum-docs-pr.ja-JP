---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718819"
---
# <a name="tail-function"></a>Tail 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列の最後の要素を返します。

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a>入力

### <a name="array--a"></a>配列: ' A []

最後の要素が取得された配列。 配列の長さは少なくとも1である必要があります。



## <a name="output--a"></a>出力: ' A

配列の最後の要素。

## <a name="type-parameters"></a>型パラメーター

### <a name="a"></a>' A

配列要素の型。