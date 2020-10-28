---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: カラム Nat 関数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719455"
---
# <a name="columnat-function"></a>カラム Nat 関数

名前空間: [Microsoft. Quantum. 配列](xref:Microsoft.Quantum.Arrays)

パック [](https://nuget.org/packages/)


マトリックスから列を抽出します。

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>説明

この関数は、行方向の順序で行列内の列を抽出します。
行 corrsponds を最初のインデックスの要素アクセスに抽出すると、それ以上の処理は必要ありません。

## <a name="input"></a>入力

### <a name="column--int"></a>列: [Int](xref:microsoft.quantum.lang-ref.int)

マトリックスの列


### <a name="matrix--t"></a>マトリックス: ' t [] []

2次元行列 (行方向)



## <a name="output--t"></a>出力: ' t []



## <a name="type-parameters"></a>型パラメーター

### <a name="t"></a>&

の各要素の型 `matrix` 。

## <a name="see-also"></a>参照

- [Microsoft... 配列. 転置](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft.................](xref:Microsoft.Quantum.Arrays.Diagonal)