---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 対角線関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719383"
---
# <a name="diagonal-function"></a>対角線関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


2次元配列の対角線要素の配列を返します。

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>説明

2次元配列が二乗図形でない場合は、行と列の数の最小値に対する対角線が返されます。

## <a name="input"></a>入力

### <a name="matrix--t"></a>マトリックス: ' t [] []

2次元行列 (行方向)



## <a name="output--t"></a>出力: ' t []



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `matrix` 。

## <a name="see-also"></a>参照

- [Microsoft... 配列. 転置](xref:Microsoft.Quantum.Arrays.Transposed)