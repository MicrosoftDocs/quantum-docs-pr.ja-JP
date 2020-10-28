---
uid: Microsoft.Quantum.Arrays.Transposed
title: 転置関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718814"
---
# <a name="transposed-function"></a>転置関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


配列の配列として表される行列の転置を返します。

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>説明

$R $ rows と $c $ columns を含む $r/倍 c $ マトリックスとして入力します。  マトリックスは行ベースであり、つまり、 `matrix[i][j]` 行 $i $ および column $j $ の要素にアクセスします。

この関数は、入力行列の転置である $c/倍 r $ matrix を返します。

## <a name="input"></a>入力

### <a name="matrix--t"></a>マトリックス: ' t [] []

行ベースの $r/倍 c $ マトリックス



## <a name="output--t"></a>出力: ' t [] []

転置 $c/x r $ matrix

## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `matrix` 。