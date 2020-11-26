---
uid: Microsoft.Quantum.Arrays.Partitioned
title: パーティション関数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220503"
---
# <a name="partitioned-function"></a>パーティション関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

