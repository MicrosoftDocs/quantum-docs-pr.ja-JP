---
uid: Microsoft.Quantum.Arrays.Transposed
title: 転置関数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850928"
---
# <a name="transposed-function"></a>転置関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パッケージ: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>例

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```