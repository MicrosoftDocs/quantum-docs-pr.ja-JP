---
uid: Microsoft.Quantum.Arrays.Partitioned
title: パーティション関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718975"
---
# <a name="partitioned-function"></a>パーティション関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列を複数の部分に分割します。

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>入力

### <a name="nelements--int"></a>nElements: [Int](xref:microsoft.quantum.lang-ref.int)[]

配列の各部分に含まれる要素の数


### <a name="arr--t"></a>arr: ' t []

分割する入力配列。



## <a name="output--t"></a>出力: ' t [] []

1番目の配列がの最初の配列で、 `nElements[0]` `arr` 2 番目の配列が次の配列である場合は、複数 `nElements[1]` の配列 `arr` 。最後の配列には、残りのすべての要素が含まれます。

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

